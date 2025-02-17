# dcc-pdf-tools

This is a JavaScript library for generating PDFs for (static) Dutch `domestic` and `european` signed proofs.

## Usage

Use this repository's `git:` URL to install the package in your project:

```sh
npm install "git://github.com:91divoc-ln/dcc-pdf-tools.git#VERSION"
```

Replace `VERSION` with the tag name of the [latest release](https://github.com/91divoc-ln/dcc-pdf-tools/releases/latest).

### In Node.js

Usage in Node.js requires polyfills for `atob` and `DOMParser`. Be sure to polyfill these before `require`ing or `import()`ing from `dcc-pdf-tools`.

E.g. using `jsdom`:

```js
const JSDOM = require("jsdom").JSDOM;
const jsdomWindow = new JSDOM().window;
global.atob = jsdomWindow.atob;
global.DOMParser = jsdomWindow.DOMParser;

const { parseProofData, getDocument } = require("dcc-pdf-tools");
```

Note: when using ES modules, it's important to use the async `import()`, as static `import`s would cause the code to be evaluated at load time, before the polyfills are installed.

## License

This project is licensed under the `EUPL-1.2`. See [LICENSE](./LICENSE).
