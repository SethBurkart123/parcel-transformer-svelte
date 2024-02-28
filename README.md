# parcel-transformer-svelte-4

A Parcel 2 transformer for Svelte 3 and 4.

## Table of Contents

1. [Installation](#installation)
2. [Configuration](#configuration)
3. [Usage](#usage)
4. [License](#license)

## Installation

```bash
npm install parcel-transformer-svelte-4 -D
```

After this you should configure in `.parcelrc` the transformation for Svelte files:

```json
{
  "extends": ["@parcel/config-default"],
  "transformers": {
    "*.svelte": ["parcel-transformer-svelte"]
  }
}
```

> To enable Svelte 4 support, you must also enable the [Exports Map feature in Parcel 2.9+](https://parceljs.org/blog/v2-9-0/#new-resolver) by padding this to package.json
```json
	"@parcel/resolver-default": {
		"packageExports": true
	},
```

## Configuration

You can change Svelte options though a `.svelterc`, `svelte.config.js` file or `svelte` field
in `package.json`.

For documentation on which options you can use look at the official
[svelte docs](https://github.com/sveltejs/svelte).

```js
// Options used by svelte.compile
compilerOptions: {
  ...
},
// Preprocessors for svelte.preprocess
preprocessors: {
  ...
}
```

## Usage

In order to use svelte inside of your project, all you need to do is initialise a small html file:
```
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Simple Svelte App</title>
  </head>
  <body class="">
    <script type="module" src="./main.ts"></script>
  </body>
</html>
```
And link it to a js (or ts) file where you import and run the app.svelte:
```
import App from './main.svelte';

const app = new App({
  target: document.body,
  props: {
    name: 'Svelte',
  },
});

export default app;
```
There you have it! That's all you need. If you are struggling feel free to open a discussion and I'll be right over to help you out!

## License

MIT License
