# Nuxt Umami <sup>@next<sup>

[![npm](https://img.shields.io/npm/v/nuxt-umami/next?style=flat-square)](https://www.npmjs.com/package/nuxt-umami/v/next)
[![Downloads](https://img.shields.io/npm/dt/nuxt-umami.svg?style=flat-square)](https://www.npmjs.com/package/nuxt-umami)
[![License](https://img.shields.io/npm/l/nuxt-umami?style=flat-square)](/LICENSE)

Deeply integrate [**Umami Analytics**](https://umami.is/) into your Nuxt websites / applications.

> **Heads up:**
> This version uses features (Nuxt Layers) that are only available in **Nuxt 3**.
> Check out [Nuxt Umami v1](https://github.com/ijkml/nuxt-umami) for Nuxt 2 compat.

## Features

- 📖 Open Source
- ✨ SSR Support, of course
- ➖ No extra script: no extra tag, no script loading, instant availability
- 😜 Escapes ad & script blockers (catch me if you can)
- 💯 Feature complete + extensive config
- ✅ Better Typescript, JSDocs, auto completion
- ✅ Error handling + debugging
- ✅ Nuxt utils + auto import

## Setup

### Step 1: Installation and add to Nuxt

Install using your favorite package manager...

```bash
pnpm add nuxt-umami@next #pnpm
```

```bash
npm install nuxt-umami@next #npm
```

Then add `nuxt-umami` to your `extends` array in `nuxt.config`:

```ts
defineNuxtConfig({
  extends: ['nuxt-umami']
});
```

Or, you can totally skip the installation process and do

```ts
defineNuxtConfig({
  extends: ['github:ijkml/nuxt-umami#next']
});
```

> **Warning**:
> This might cause unwanted errors due to changes as the branch is still WIP.

### Step 2: Configure Umami

You can provide configuration options using the `app.config.ts` file or `appConfig` property of the Nuxt config.

#### `app.config.ts` file

(recommended for readability and ease of update)

```ts
export default defineAppConfig({
  umami: {
  // ...umami config here
  },
});
```

#### `appConfig` property

```ts
defineNuxtConfig({
  extends: ['nuxt-umami@next'],
  appConfig: {
    umami: {
      // ...umami config here
    },
  },
});
```

### Step 3:

Use it?

## Configuration

| option | type | description | required | default |
|---|---|---|---|---|
| host | string | Your Umami endpoint. This is where your script is hosted. Eg: `https://ijkml.xyz/`. | yes | '' |
| id | string | Unique website-id provided by Umami. | yes | '' |
| domains | string | Limit tracker to specific domains by providing a comma-separated list (without 'http'). Leave blank for all domains. | no | '' |
| ignoreDnt | boolean | Option to ignore browsers' Do Not Track setting. | no | true |
| autoTrack | boolean | Option to automatically track page views. | no | true |
| ignoreLocalhost | boolean | Option to prevent tracking on localhost. | no | false |
| version | `1 \| 2`  | Umami version (Cloud) | no | `1` |

## Usage

Two functions are auto-imported, `umTrackView()` and `umTrackEvent()`. Use them however and wherever you like.

### Available Methods

- `umTrackView(url, referrer)`
  - `url`: the path being tracked, eg `/about`, `/contact?by=phone#office`. *Most times*, this can be correctly inferred. Equivalent of `router.fullPath`.
  - `referrer`: the page referrer. *Most times*, this can be correctly inferred. Equivalent of `document.referrer`.

- `umTrackEvent(eventName, eventData)`
  - `eventName`: a string type text
  - `eventData`: an object in the format `{key: value}`, where `key` is a string and `value` is a string, number, or boolean.


Reference: [Umami Tracker Functions](https://umami.is/docs/tracker-functions).


## Umami Cloud, v2

Umami v2's release is on the horizon, and they currently offer a [free beta plan](https://umami.is/pricing) for Umami Cloud. To use v2 (or Cloud), set `version: 2` in the Umami config.

> **Warning**:
> v2 is still WIP pending official release and the new docs. Test rigorously, and if you encounter bugs/issues, please open an issue.

## Issues, Bugs, Ideas?

Open an issue, fire a PR. Contributions are welcome! If you encounter any issues, don't hesitate to open an issue. I'm always available to help and resolve any bugs.

## Contributors

<a href="https://github.com/ijkml/nuxt-umami/graphs/contributors">
  <img alt="Nuxt Umami contributors" src="https://contrib.rocks/image?repo=ijkml/nuxt-umami" />
</a>

[MIT](./LICENSE) License © 2023 [ML](https://github.com/ijkml/)
