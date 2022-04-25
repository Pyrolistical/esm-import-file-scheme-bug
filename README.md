# esm-import-file-scheme-bug

version 12 results

```sh
$ npm start

> esm-import-file-scheme-bug@ start /Users/rchen/dev/projects/github.com/Pyrolistical/esm-import-file-scheme-bug
> ls *.js|xargs -I FILE -n 1 bash -c 'echo running FILE && node FILE'

running absolute-import-expected-to-work-but-does-not.js
internal/process/esm_loader.js:74
    internalBinding('errors').triggerUncaughtException(
                              ^

TypeError [ERR_INVALID_URL]: Invalid URL: /Users/rchen/dev/projects/github.com/Pyrolistical/esm-import-file-scheme-bug/inner.js
    at onParseError (internal/url.js:258:9)
    at new URL (internal/url.js:334:5)
    at Loader.defaultResolve [as _resolve] (internal/modules/esm/resolve.js:778:5)
    at Loader.resolve (internal/modules/esm/loader.js:100:40)
    at Loader.getModuleJob (internal/modules/esm/loader.js:246:28)
    at ModuleWrap.<anonymous> (internal/modules/esm/module_job.js:47:40)
    at link (internal/modules/esm/module_job.js:46:36) {
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
    at onParseError (internal/url.js:258:9)
    at new URL (internal/url.js:334:5)
    at Loader.defaultResolve [as _resolve] (internal/modules/esm/resolve.js:778:5)
    at Loader.resolve (internal/modules/esm/loader.js:100:40)
    at Loader.getModuleJob (internal/modules/esm/loader.js:246:28)
    at ModuleWrap.<anonymous> (internal/modules/esm/module_job.js:47:40)
    at link (internal/modules/esm/module_job.js:46:36) {
  input: './inner.js',
  code: 'ERR_INVALID_URL'
}
```
