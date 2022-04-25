# esm-import-file-scheme-bug

version 16 results

```sh
$ npm start

> start
> ls *.js|xargs -I FILE -n 1 bash -c 'echo running FILE && node FILE'

running absolute-import-expected-to-work-but-does-not.js
node:internal/errors:464
    ErrorCaptureStackTrace(err);
    ^

TypeError [ERR_INVALID_URL]: Invalid URL
    at new NodeError (node:internal/errors:371:5)
    at onParseError (node:internal/url:552:9)
    at new URL (node:internal/url:628:5)
    at moduleResolve (node:internal/modules/esm/resolve:971:16)
    at defaultResolve (node:internal/modules/esm/resolve:1080:11)
    at ESMLoader.resolve (node:internal/modules/esm/loader:530:30)
    at ESMLoader.getModuleJob (node:internal/modules/esm/loader:251:18)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/module_job:79:40)
    at link (node:internal/modules/esm/module_job:78:36) {
  input: '/Users/rchen/dev/projects/github.com/Pyrolistical/esm-import-file-scheme-bug/inner.js',
  code: 'ERR_INVALID_URL'
}
running file-scheme-import-expected-to-work-but-does-not.js
inner
running inner.js
inner
running only-data-url-works.js
inner
running relative-import-expected-to-fail.js
node:internal/errors:464
    ErrorCaptureStackTrace(err);
    ^

TypeError [ERR_INVALID_URL]: Invalid URL
    at new NodeError (node:internal/errors:371:5)
    at onParseError (node:internal/url:552:9)
    at new URL (node:internal/url:628:5)
    at moduleResolve (node:internal/modules/esm/resolve:971:16)
    at defaultResolve (node:internal/modules/esm/resolve:1080:11)
    at ESMLoader.resolve (node:internal/modules/esm/loader:530:30)
    at ESMLoader.getModuleJob (node:internal/modules/esm/loader:251:18)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/module_job:79:40)
    at link (node:internal/modules/esm/module_job:78:36) {
  input: './inner.js',
  code: 'ERR_INVALID_URL'
}
```
