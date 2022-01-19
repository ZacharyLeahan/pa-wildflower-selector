# pa-wildflower-selector

## Project setup

First install the imagemagick command line utilities and MongoDB community edition on your machine, including the MongoDB command line utilities.

Then you can install the npm dependencies at the server app and ui app levels:

```
npm install
cd ui
npm install
cd ..
```

## First time and occasional stuff

### Download a copy of the database

Run:

```
npm restore-test-data
```

You can also rebuild it from scratch, but this takes hours to run because of the need to obtain images from wikipedia and wikimedia:

```
node app download
```

Then run the `massage` script to clean up the data into a more reasonable form for queries:

```
node app massage
```

## Routine stuff

### Start up both a local server and the frontend app
```
npm run dev
```

### Compiles and minifies for production
```
npm run build
```

### Tests the production experience locally
```
npm run ssr-dev
```

This is much slower and doesn't restart automatically, but it is important to check before deploying to production, in order to make sure we haven't broken server side rendering with changes to the Vue application that are browser-specific. If you must do something browser-specific, wrap it in an `if ((typeof window) !== 'undefined') { ... }` block.

### Deploys (to Tom's server, currently for Tom to run)
```
npm run deploy
```

### Where is the UI code?

In `src/`.

### Where is the server-side app code that answers queries?

In the main folder of the project.
