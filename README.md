# Resolve URL Loader

Webpack loader that resolves relative paths in url() statements based on the original source file.

Use in conjunction with the [sass-loader](https://www.npmjs.com/package/sass-loader) and specify your asset `url()` relative to the `.scss` file in question.

This loader will use the source-map from the SASS compiler to locate the original `.scss` source file and write a more Webpack-friendly path for your asset. The CSS loader can then locate your asset for individual processing.


## Getting started

See [resolve-url-loader](packages/resolve-url-loader/README.md) package in this mono-repo.


## Version 3.0.0

The target for the next major version

- [x] Allow additional CSS "engines" (e.g. postcss)

- [x] Move the file search to a separate package as "opt in"

- [x] Automated tests E2E

  * test-my-cli
  - [x] basic tests
  - [x] tests run on both Mac and Windows
  - [x] better ENV `append` (rename to `merge`)
    - [x] regex key matching
    - [x] custom merge fn

  * resolve-url-loader
  - [x] check some typical directory structures
  - [x] check `keepQuery` option
  - [x] check URIs with protocols are not processed
  - [x] check `absolute` option
  - [x] check `debug` option
  - [x] check `root` option
  - [x] check defunct options lead to warnings
  - [x] check `silent` option supresses warnings
  - [x] check invalid `join` and `root` options lead to errors
  - [x] check `silent` option doesn't supresses errors
  - [x] check bad CSS gives expected error
  - [x] check sourcemaps

- [x] Attempt a basic Postcss Engine (to ensure restructure is adequate)

- [ ] Rewrite README.md
  * Windows backslash paths _must_ be processed _before_ css loader.
  * [Breaking] Multiple options changed or deprecated. Warnings are provided subject to `silent` option.
  * [Breaking] Errors always fail and are no longer swallowed.
  * [Breaking] File search not supported (`join` option available).
  * [Breaking] Processing absolute URI requires `root` option to be set (may be empty string).
  * [Breaking] Where specified, `root` option must be empty string or absolute path.
