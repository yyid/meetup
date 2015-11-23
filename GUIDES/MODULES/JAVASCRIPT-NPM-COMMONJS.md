# JAVASCRIPT + NPM + COMMONJS

## Description

This is the standard way to package node (server-side) modules. The package manager is [npm](???). The format you package your modules in is called [CommonJS](???).

Nevertheless, you can also use NPM for client-side code, but you will need a tool that handles the module loading in the browser and/or packages all code into a single bundle file. Such tools include:

- [Browserify]()
- [Webpack]()
- [System.js]()

## How to Package a Module

### Recommended File Structure

TBD

You should also add information and documentation to your module, by adding a `README.md`, a `LICENSE.txt`, and a `CHANGELOG.md` file.

### `package.json`

The `package.json` file contains your module's meta data. You can interactively create one using `$ npm init`

[Documentaton](https://docs.npmjs.com/files/package.json)

```json
{
  "name": "mmm",
  "version": "0.1.0",
  "description": "Description",
  "homepage": "https://github.com/micromodules/meetup",
  "repository": {
    "type": "git",
    "url": "git://github.com/micromodules/meetup.git"
  },
  "author": {
    "name": "Jane Doe",
    "email": "mail@moremicromodules.org",
    "url": "http://moremicromodules.org"
  },
  "keywords": [
    "micro",
    "module"
  ],
  "main": "mmm.js",
  "dependencies": {
  },
  "devDependencies": {
  },
  "license": "MIT"
}
```

TBD: Describe how to add dependencies

## How to Publish a Module

TBD: Register

In the module directory run:

```shell
$ npm publish
```

## Resources

TBD
