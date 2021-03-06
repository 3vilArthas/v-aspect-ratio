# v-aspect-ratio

> Vue.js directive for setting an aspect ratio

[![BuildStatus](https://img.shields.io/github/workflow/status/andrewvasilchuk/v-aspect-ratio/Integration)](https://github.com/andrewvasilchuk/v-aspect-ratio/actions?query=workflow%3AIntegration)
[![Version](https://img.shields.io/npm/v/v-aspect-ratio)](https://www.npmjs.com/package/v-aspect-ratio)
[![Bundle Size](https://img.shields.io/bundlephobia/minzip/v-aspect-ratio)](https://bundlephobia.com/result?p=v-aspect-ratio)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/0a12c2d8dbd44f028aacddb254df983d)](https://www.codacy.com/gh/andrewvasilchuk/v-aspect-ratio/dashboard?utm_source=github.com&utm_medium=referral&utm_content=andrewvasilchuk/v-aspect-ratio&utm_campaign=Badge_Grade)
[![Total alerts](https://img.shields.io/lgtm/alerts/g/andrewvasilchuk/v-aspect-ratio.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/andrewvasilchuk/v-aspect-ratio/alerts/)
[![Language grade: JavaScript](https://img.shields.io/lgtm/grade/javascript/g/andrewvasilchuk/v-aspect-ratio.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/andrewvasilchuk/v-aspect-ratio/context:javascript)
[![codecov](https://codecov.io/gh/andrewvasilchuk/v-aspect-ratio/branch/master/graph/badge.svg)](https://codecov.io/gh/andrewvasilchuk/v-aspect-ratio)
[![Downloads](https://img.shields.io/npm/dt/v-aspect-ratio)](https://www.npmjs.com/package/v-aspect-ratio)
[![LastCommit](https://img.shields.io/github/last-commit/andrewvasilchuk/v-aspect-ratio)](https://github.com/andrewvasilchuk/v-aspect-ratio/commits/master)
[![License](https://img.shields.io/npm/l/v-aspect-ratio)](https://github.com/andrewvasilchuk/v-aspect-ratio/blob/master/LICENSE)
[![MadeWithVueJs.com shield](https://madewithvuejs.com/storage/repo-shields/2800-shield.svg)](https://madewithvuejs.com/p/v-aspect-ratio/shield-link)

`1.x` documentation can be found [here](https://github.com/andrewvasilchuk/v-aspect-ratio/tree/1.x).

![Computer screens with different aspect ratios](./assets/img.jpg)

- [v-aspect-ratio](#v-aspect-ratio)
  - [Installation](#installation)
    - [Via NPM](#via-npm)
    - [Via Yarn](#via-yarn)
    - [Directly in browser](#directly-in-browser)
  - [Initialization](#initialization)
    - [As a global plugin](#as-a-global-plugin)
    - [As a global directive](#as-a-global-directive)
    - [As a local directive](#as-a-local-directive)
    - [As a Nuxt.js SSR directive](#as-a-nuxtjs-ssr-directive)
    - [Directly in browser](#directly-in-browser-1)
  - [Usage](#usage)
  - [Demo](#demo)
  - [Tests](#tests)
  - [Development](#development)
  - [Build](#build)
  - [License](#license)

## Installation

### Via NPM

```bash
$ npm install v-aspect-ratio --save
```

### Via Yarn

```bash
$ yarn add v-aspect-ratio
```

### Directly in browser

```html
<script src="https://unpkg.com/v-aspect-ratio"></script>
```

## Initialization

### As a global plugin

It must be called before `new Vue()`

```js
import Vue from 'vue'
import AspectRatio from 'v-aspect-ratio'

Vue.use(AspectRatio)
```

### As a global directive

```js
import Vue from 'vue'
import { directive } from 'v-aspect-ratio'

Vue.directive('aspect-ratio', directive)
```

### As a local directive

```javascript
import { directive } from 'v-aspect-ratio'

export default {
  name: 'YourAwesomeComponent',
  directives: {
    'aspect-ratio': directive,
  },
}
```

### As a Nuxt.js SSR directive

```js
// nuxt.config.js

const {
  directive,
} = require('v-aspect-ratio/dist/v-aspect-ratio.ssr.common.js')

module.exports = {
  // ...
  render: {
    bundleRenderer: {
      directives: {
        'aspect-ratio': directive,
      },
    },
  },
  // ...
}
```

### Directly in browser

```html
<!-- As a global directive -->
<script>
  Vue.use(VAspectRatio.default)
  new Vue({
    // ...
  })
</script>
<!-- As a local directive -->
<script>
  new Vue({
    // ...
    directives: { 'aspect-ratio': VAspectRatio.directive },
    // ...
  })
</script>
```

## Usage

```html
<template>
  <div>
    <div v-aspect-ratio="'16:9'"></div>
    <div v-aspect-ratio="'4:3'"></div>
  </div>
</template>
```

## Demo

[Demo](https://andrewvasilchuk.github.io/v-aspect-ratio)

[![Demo](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/ko425ro4k7)

## Tests

[`jest`](https://jestjs.io) and [`@vue/test-utils`](https://vue-test-utils.vuejs.org) is used for unit tests.

You can run unit tests by running the next command:

```bash
npm run test
```

## Development

1. Clone this repository
2. Install the dependencies running `yarn install` or `npm install` command
3. Start a development server using `npm run dev` command

## Build

To build the production ready bundle simply run `npm run build`:

After the successful build the following files will be generated in the `dist` folder:

```
├── plugin
  ├── index.d.ts
├── directive.d.ts
├── helpers.d.ts
├── index.d.ts
├── v-aspect-ratio.common.js
├── v-aspect-ratio.esm.js
├── v-aspect-ratio.js
├── v-aspect-ratio.min.js
├── v-aspect-ratio.ssr.common.js
├── v-aspect-ratio.ssr.esm.js
├── v-aspect-ratio.ssr.js
├── v-aspect-ratio.ssr.min.js
```

## License

[MIT](http://opensource.org/licenses/MIT)
