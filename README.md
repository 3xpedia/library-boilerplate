# Simple boilerplate for JavaScript libraries

### Included with this boilerplate

- Eslint and prettier config
- Build scripts that output ESM, CJS and browser global. Write your code in ESM, export it anywhere
- As parcel does support TypeScript (among other stuff) out of the box, this library boilerplate does also support TypeScript.

### How to use

- Clone this repo
- Update relevant information (license, author, ...) in the `package.json`
- Write your code in `./src`. You can also change the exports in the `index.*` files to match your needs.
- You are good to publish

### How to build and publish

- `npm run build` to build your library
- `npm publish` to publish it on NPM
- There is also a `npm run watch` script that will watch and rebuild for local development.

### What is in the build

- `./dist/index.cjs` and `./dist/index.mjs` respectively contains CJS and ESM build. The host environment should be able to pick the right build automatically.
- `./dist/index.browser.js` provide a static build for web-browsers. It exposes you library on the global object. It also packages all the required modules from the `node_modules`

### How to import the lib

- CJS

```javascript
const myLib = require("myLib");

// OR (depends on how you export the lib in index.cjs)

const { foo, bar } = require("myLib");
```

- ESM
```javascript
import myLib from "myLib";

// OR (depends on how you export the lib in index.mjs)

import { foo, bar } from "myLib"
```

- Browser
```javascript
<script src="myLib.js"></script>
<script>
  myLib.foo();
  
  // OR
  
  myLib();
</script>
```

### Known issues

- No babel config is provided. Parcel does already ensure compatibility via the `browserList` key in the `package.json`. But it should be easy to add any required babel config see [parcel doc](https://parceljs.org/languages/javascript/#babel)
- Host using a Node version prior to 12.17.0 may have troubles finding the right module system as they do not recognise the `exports` key in the `package.json`. As Node 12.x has reached EOL in April 2022, I decided this is a non-issue even if easily fixable.
