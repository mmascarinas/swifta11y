[![npm version](https://img.shields.io/npm/v/eslint.svg)](https://www.npmjs.com/package/eslint)

<br />

# swiftA11y

An AI-based accessibiliy linting tool forked from ESLint.

* ESLint uses [Espree](https://github.com/eslint/espree) for JavaScript parsing.
* ESLint uses an AST to evaluate patterns in code.
* ESLint is completely pluggable, every single rule is a plugin and you can add more at runtime.
* Uses an OpenAI wrapper extension to fix the accessiblity issues based of ESlint accessibility plugins.

## Installation

Prerequisites: [Node.js](https://nodejs.org/) (`^18.18.0`, `^20.9.0`, or `>=21.1.0`) built with SSL support. (If you are using an official Node.js distribution, SSL is always built in.)

Please install swifta11y using this command. :

```shell
npm install swifta11y
```

Along with swifta11y, couple of eslint plugins needs to be installed in your project packages. Please install by running the following command. :

```shell
npm install eslint-plugin-vue-a11y --legacy-peer-deps
```
```shell
npm install eslint-plugin-vuejs-accessibility
```

After that, create a config file named .swifta11yrc.js . Please run the following command :

```shell
touch .swifta11yrc.js
```

## Configuration

Place the following recommended config inside .swifta11yrc.js :

```javascript
module.exports = {
  root: true,
  env: {
    browser: true,
    node: true
  },
  parserOptions: {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  extends: [
    "plugin:vue-a11y/base",
    "plugin:vue-a11y/recommended",
    "plugin:vuejs-accessibility/recommended"
  ],
  plugins: ["vuejs-accessibility", "vue-a11y"]
}
```

## Usage

Finally, to run swifta11y inorder to display the accessibility issues in the console, run the following command :

```shell
swifta11y --ext .js,.vue .
```

If you want the accessibility issues in your app codebase fixed automatically through the integrated AI plugin, run the following :

```shell
swifta11y --fix --ext .js,.vue . .
```

Alternatively, you can add the following in the script property of your app's package.json;
```json
  "scripts": {
    "lint": "swifta11y --ext .js,.vue .",
    "lintfix": "swifta11y --fix --ext .js,.vue .",
  },
```

And just simply run;
```shell
npm run lint
```

or

```shell
npm run lintfix
```

respectively


## Disclaimer

Note: This project is primarily derived from ESlint package authored by Nicholas C. Zakas <nicholas+npm@nczconsulting.com> of eslint.org.
We want to clarify that our sole intention for creating this version is to extend the functionalities of this open-source project to cater to our specific needs. We acknowledge and appreciate the primal contributions made by the eslint.org community and strive to adhere to the principles of respectful and collaborative software development.
