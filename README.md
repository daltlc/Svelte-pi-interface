This application was made for my personal rasberry pi as a central dashboard with some of different things I check out each morning, including news, crypto currency prices, and the weather.

This was built for a fixed screen size, responsiveness wasn't needed.

This was a project to familiarize myself with Svelte. 

If you wish to fork this and use for yourself, keep in mind you will need to create your own data folder within src with users.js and apikeys.js. The structure for users will be below, you will need to get your own api key for the crypto and weather component yourself. https://api.openweathermap.org, https://api.cryptonator.com.

```
export default [
    {
        username: 'Dalton',
        pin: '5555',
        icon: '',
        color:'#191E4E'
    }
]
```


This is hosted on netlify at: https://svelte-pi.netlify.com

Input pin 5555 for my demo dashboard.

---

# svelte app

This is a project template for [Svelte](https://svelte.dev) apps. It lives at https://github.com/sveltejs/template.

To create a new project based on this template using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit sveltejs/template svelte-app
cd svelte-app
```

*Note that you will need to have [Node.js](https://nodejs.org) installed.*


## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.


## Deploying to the web

### With [now](https://zeit.co/now)

Install `now` if you haven't already:

```bash
npm install -g now
```

Then, from within your project folder:

```bash
cd public
now
```

As an alternative, use the [Now desktop client](https://zeit.co/download) and simply drag the unzipped project folder to the taskbar icon.

### With [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public
```
