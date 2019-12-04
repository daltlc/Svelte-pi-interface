<script>
  import Keypad from "./Keypad.svelte";
  import Dashboard from "./Dashboard.svelte";
  import { onMount } from "svelte";
  import { writable } from "svelte/store";
  import Users from "./data/users.js"

  let pin;
  let user = { loggedIn: false };
  let currentUser;
  let currentTheme;
  let invalid = false;
  $: view = pin ? pin.replace(/\d(?!$)/g, "*") : "Enter your pin";

  onMount(() => {
    console.log(Users)
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
    for (let i = 0; i < Users.length; i++) {
      if (Users[i].pin === pin) {
        user.loggedIn = true;
        currentUser = Users[i].username;
        currentTheme = Users[i].color;
        localStorage.setItem("user", Users[i].username);
        localStorage.setItem("theme", Users[i].color);
        localStorage.setItem("pin", Users[i].pin);
      } else {
      }
    }
  };
  let logOut = () => {
     localStorage.clear();
     location.reload();
  }
</script>

<style>
  .main-app {
    background-color: #232f34;
    min-height: 90vh;
  }
  .welcome {
    color: white;
    padding-top: 10px;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    font-weight: 500;
    font-size: 40px;
    padding-bottom: 10px;
    font-family: "Montserrat", sans-serif;
  }
  h1 {
    color: white;
    padding-left: 40px;
    margin-bottom: 20px;
    margin-top: 0px;
    font-family: "Montserrat", sans-serif;
  }
  .nav {
    display: flex;
    justify-content: space-between;
    background-color: #06081b;
  }
  .log-out {
    margin-right: 40px;
    color: white;
    font-family: "Montserrat", sans-serif;
    background-color: #06081b;
    border:none;
    cursor:pointer;
  }
</style>

<div class="main-app">
  {#if !user.loggedIn}
    <h1 class="welcome">
      Welcome to
      <span style="color:#F9AA33;">Scope</span>
    </h1>
    <h1 style="color: {pin ? '#F9AA33' : '#ccc'}">{view}</h1>
    <Keypad bind:value={pin} on:submit={pinSubmit} />
  {/if}
  {#if user.loggedIn}
    <div class="dashboard" style="background-color: {currentTheme}">
      <div class="nav">
        <h1 class="welcome">Welcome {currentUser}</h1>
        <button on:click|once={logOut} class="log-out">Log out</button>
      </div>
      <!-- This will be the setting gear component -->
      <!-- <Settings/> -->
      <!--pass user with dashboard as prop to render correct apps-->
      <Dashboard user={currentUser} />
    </div>
  {/if}
</div>
