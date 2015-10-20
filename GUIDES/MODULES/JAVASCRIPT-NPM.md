# JAVASCRIPT + NPM

## Requirements

TBD

## How to Package a Module

### Recommended File Structure

TBD

You should also add information and documentation to your module, by adding a `README.md`, a `LICENSE.txt`, and a `CHANGELOG.md` file.

### `package.json`

The `package.json` file contains your module's meta data. You can also interactively creato one using `$ npm init`

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