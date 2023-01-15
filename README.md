# Simple boilerplate for JavaScript libraries

### Included with this boilerplate

- Eslint and prettier config
- Rollup and babel config
- Build script that packages everything in `dist` folder (along with packages.json, license, readme and changelog)

### How to use

- Clone this repo
- Update relevant information (license, author, ...)
- Update MODULE_NAME in `rollup.config.js`
- You are good to go

### How to build and publish

- `npm run build` to build (will also copy relevant files in the `dist` folder)
- `cd ./dist` to move in the dist folder (or any command relevant to your OS)
- `npm publish` to publish the package on the npm repository
