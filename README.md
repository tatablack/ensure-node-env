# ensure-node-env

[![Build Status](https://travis-ci.org/Skyscanner/ensure-node-env.svg?branch=master)](https://travis-ci.org/Skyscanner/ensure-node-env) [![Greenkeeper badge](https://badges.greenkeeper.io/Skyscanner/ensure-node-env.svg)](https://greenkeeper.io/)

A script that helps ensure you have the correct node &amp; npm versions installed globally in your environment.

## Usage

Add the following to your `package.json`:

```json
  ...
  "engines": {
    "node": "^8.9.0",
    "npm": "^6.4.1"
  },
  "scripts": {
    "preinstall": "npx ensure-node-env",
    ...
```

Where the `node` and `npm` engine properties specify a valid semver range for Node and npm version respectively.


### Usage in libraries

This script is designed to be used as a development-only preinstall check in the project root. For libraries that are published and consumed in other projects it is considered good enough to include it as a pretest check:

```sh
npm install ensure-node-env --save-dev
```

```json
  ...
  "engines": {
    "node": "^8.9.0",
    "npm": "^6.4.1"
  },
  "scripts": {
    "pretest": "ensure-node-env",
    ...
```

## Guide

Skyscanner Node development requires Node LTS and npm `^6.4.1`. [Nvm](https://github.com/creationix/nvm) users can run `nvm use` to switch to `lts/carbon`. [Nave](https://github.com/isaacs/nave) users can use `nave auto`. You can also download Node LTS using [the website](https://nodejs.org/en/). To install npm `^6.4.1`, run `npm install -g npm@^6.4.1`.
