# monorepo-yarn-typescript

## explanation

This repository shows a simple way to create a monorepo (where X applications can use a shared package - e.g. for shared UI, scripts, services, models or whatever).

The solution I built uses [Yarn Workspaces](https://classic.yarnpkg.com/lang/en/docs/workspaces), [Yarn PnP](https://yarnpkg.com/features/pnp) and [Node.js Corepack](https://nodejs.org/dist/latest/docs/api/corepack.html).

## requirements

* Node.js 18+ (`v18.13.0`)
* Yarn `4.0.1` (managed by [corepack](https://nodejs.org/api/corepack.html)):
  1. `$ npm uninstall -g yarn`
  2. `$ npm install -g corepack`
  3. `$ corepack enable`

## setup

* install dependencies (generate `.pnp.cjs` file):

```sh
$ yarn
```

* run compilation process for `shared` package (in watch mode):

```sh
$ yarn workspace shared watch # tsc --watch
```

* run compilation process for `app1` package (in watch mode):

```sh
$ yarn workspace app1 watch # tsc --watch
```

* execute `app1` output:

```sh
$ yarn workspace app1 node dist/src/index.js
```

## TODO

1. production build instruction
2. packages versioning
