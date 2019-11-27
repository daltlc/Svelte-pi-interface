<script>
  import Keypad from "./Keypad.svelte";
  import Dashboard from "./Dashboard.svelte";
  import { onMount } from "svelte";
  import { writable } from "svelte/store";

  let pin;
  let user = { loggedIn: false };
  let currentUser;
  let currentTheme;
  let invalid = false;
  $: view = pin ? pin.replace(/\d(?!$)/g, "*") : "Enter your pin";

  let users = [
    {
      username: "Dalton",
      pin: "5555",
      icon: "",
      color: "#F9AA33"
    },
    {
      username: "Carissa",
      pin: "0143",
      icon: "",
      color: "blue"
    }
  ];

  onMount(() => {
    let savedUser = localStorage.getItem("user");
    let savedTheme = localStorage.getItem("theme");
    let savedPin = localStorage.getItem("pin");
    if (savedUser && savedTheme && savedPin) {
      user.loggedIn = true;
      currentUser = savedUser;
      currentTheme = savedTheme;
    }
  });

  const pinSubmit = () => {
    for (let i = 0; i < users.length; i++) {
      if (users[i].pin === pin) {
        user.loggedIn = true;
        currentUser = users[i].username;
        currentTheme = users[i].color;
        localStorage.setItem("user", users[i].username);
        localStorage.setItem("theme", users[i].color);
        localStorage.setItem("pin", users[i].pin);
      } else {
      }
    }
  };
</script>

<style>

.main-app{
  background-color: #232F34;
}
.welcome{
  color:white;
  padding-top:10px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-weight:500;
  font-size:40px;
  padding-bottom:10px;
}
  h1 {
    color: white;
    padding-left:40px;
    margin-bottom:20px;
    margin-top:0px;
  }
</style>
<div class="main-app">
{#if !user.loggedIn}
  <h1 class="welcome">Welcome to <span style="color:#F9AA33;">Scope</span></h1>
  <h1 style="color: {pin ? '#F9AA33' : '#ccc'}">{view}</h1>
  <Keypad bind:value={pin} on:submit={pinSubmit} />
{/if}
{#if user.loggedIn}
  <div class="dashboard" style="background-color: {currentTheme}">
    <h1 class="welcome">Welcome {currentUser}</h1>
    <!-- This will be the setting gear component -->
    <!-- <Settings/> -->
    <Dashboard />
  </div>
{/if}
</div>
