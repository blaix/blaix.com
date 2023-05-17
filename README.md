# README

This is a starter to try the elm-pages 3.0 with express.js.

## Setup Instructions

`npm install` from the cloned repo. Before running the dev server or build, make sure to install Lamdera (see below).

`npm run dev` starts the dev server with hot reloading.

`npm run build` builds the app for production.

`npm starts` starts the production server at `server.mjs`.

### Install Lamdera

[Install Lamdera with these instructions](https://dashboard.lamdera.app/docs/download).

`elm-pages` 3.0 uses the lamdera compiler, which is a superset of the Elm compiler with some extra functionality to automatically serialize Elm types to Bytes. That means there is no more `OptimizedDecoder` API, you can just use regular `elm/json` Decoders! And no more `DataSource.distill`, since types are now automatically serialized all those optimizations come for free.

### Debugging Lamdera Errors

Sometimes Lamdera will give compiler errors due to corrupted dependency cache. These messages will display a note at the bottom:

```text
-- PROBLEM BUILDING DEPENDENCIES ---------------

...


Note: Sometimes `lamdera reset` can fix this problem by rebuilding caches, so
give that a try first.
```

Be sure to use `lamdera reset` to reset the caches for these cases. See more info about that in the Lamdera docs:
<https://dashboard.lamdera.app/docs/ides-and-tooling#problem-corrupt-caches>

### Docs

Check out [the 3.0 Package Docs](https://package.elm-lang.org/packages/dillonkearns/elm-pages-v3-beta/latest/). The 3.0 docs are still a work in progress.

You can also use `npx elm-pages docs` from your project to view the documentation for the `RouteBuilder` module.

## Running Scripts with `elm-pages run`

- `npm install`
- `npx elm-pages run script/src/AddRoute.elm User.Id_` - now you can try out the generator! And you can tweak it, or even define new generator modules in the `script/` folder! You can also shorten this command to `npx elm-pages run AddRoute User.Id_` if you prefer.
