# esm-import-file-scheme-bug

version 14 results

```sh
$ npm start

> esm-import-file-scheme-bug@ start /Users/rchen/dev/projects/github.com/Pyrolistical/esm-import-file-scheme-bug
> ls *.js|xargs -I FILE -n 1 bash -c 'echo running FILE && node FILE'

running absolute-import-expected-to-work-but-does-not.js
internal/process/esm_loader.js:74
    internalBinding('errors').triggerUncaughtException(
                              ^

TypeError [ERR_INVALID_URL]: Invalid URL: /Users/rchen/dev/projects/github.com/Pyrolistical/esm-import-file-scheme-bug/inner.js
    at new NodeError (internal/errors.js:322:7)
    at onParseError (internal/url.js:270:9)
    at new URL (internal/url.js:346:5)
    at Loader.defaultResolve [as _resolve] (internal/modules/esm/resolve.js:867:5)
    at Loader.resolve (internal/modules/esm/loader.js:89:40)
    at Loader.getModuleJob (internal/modules/esm/loader.js:242:28)
    at ModuleWrap.<anonymous> (internal/modules/esm/module_job.js:76:40)
    at link (internal/modules/esm/module_job.js:75:36) {
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
internal/process/esm_loader.js:74
    internalBinding('errors').triggerUncaughtException(
                              ^

TypeError [ERR_INVALID_URL]: Invalid URL: ./inner.js
    at new NodeError (internal/errors.js:322:7)
    at onParseError (internal/url.js:270:9)
    at new URL (internal/url.js:346:5)
    at Loader.defaultResolve [as _resolve] (internal/modules/esm/resolve.js:867:5)
    at Loader.resolve (internal/modules/esm/loader.js:89:40)
    at Loader.getModuleJob (internal/modules/esm/loader.js:242:28)
    at ModuleWrap.<anonymous> (internal/modules/esm/module_job.js:76:40)
    at link (internal/modules/esm/module_job.js:75:36) {
  input: './inner.js',
  code: 'ERR_INVALID_URL'
}
```
