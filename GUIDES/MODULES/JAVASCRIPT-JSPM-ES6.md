# JAVASCRIPT + JSPM + ES6 MODULES

## Description

This is a way to package JavaScript libraries that aims to be future proof. [JSPM](???) is a package manager that wraps around [npm] and [github]. Under the hood, JSPM uses [System.js] to load arbitrary module formats, including  [ES6-sytle  modules](surl).

## How to Package a Module

### Recommended File Structure

    .   
    ├── Gemfile
    ├── lib 
    │   ├── mmm 
    │   │   └── version.rb
    │   └── mmm.rb
    ├── mmm.gemspec
    └── Rakefile

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
