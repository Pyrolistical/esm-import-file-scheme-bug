# esm-import-file-scheme-bug

version 18 results
```sh
$ npm start

> start
> ls *.js|xargs -I FILE -n 1 bash -c 'echo running FILE && node FILE'

running absolute-import-expected-to-work-but-does-not.js
node:internal/errors:465
    ErrorCaptureStackTrace(err);
    ^

TypeError [ERR_INVALID_URL_SCHEME]: The URL must be of scheme file
    at new NodeError (node:internal/errors:372:5)
    at fileURLToPath (node:internal/url:1484:11)
    at checkIfDisallowedImport (node:internal/modules/esm/resolve:1018:23)
    at defaultResolve (node:internal/modules/esm/resolve:1147:23)
    at ESMLoader.resolve (node:internal/modules/esm/loader:605:30)
    at ESMLoader.getModuleJob (node:internal/modules/esm/loader:318:18)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/module_job:80:40)
    at link (node:internal/modules/esm/module_job:78:36) {
  code: 'ERR_INVALID_URL_SCHEME'
}

Node.js v18.0.0
running file-scheme-import-expected-to-work-but-does-not.js
node:internal/errors:465
    ErrorCaptureStackTrace(err);
    ^

TypeError [ERR_INVALID_URL_SCHEME]: The URL must be of scheme file
    at new NodeError (node:internal/errors:372:5)
    at fileURLToPath (node:internal/url:1484:11)
    at checkIfDisallowedImport (node:internal/modules/esm/resolve:1018:23)
    at defaultResolve (node:internal/modules/esm/resolve:1147:23)
    at ESMLoader.resolve (node:internal/modules/esm/loader:605:30)
    at ESMLoader.getModuleJob (node:internal/modules/esm/loader:318:18)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/module_job:80:40)
    at link (node:internal/modules/esm/module_job:78:36) {
  code: 'ERR_INVALID_URL_SCHEME'
}

Node.js v18.0.0
running inner.js
inner
running only-data-url-works.js
inner
running relative-import-expected-to-fail.js
node:internal/errors:465
    ErrorCaptureStackTrace(err);
    ^

TypeError [ERR_INVALID_URL_SCHEME]: The URL must be of scheme file
    at new NodeError (node:internal/errors:372:5)
    at fileURLToPath (node:internal/url:1484:11)
    at checkIfDisallowedImport (node:internal/modules/esm/resolve:1018:23)
    at defaultResolve (node:internal/modules/esm/resolve:1147:23)
    at ESMLoader.resolve (node:internal/modules/esm/loader:605:30)
    at ESMLoader.getModuleJob (node:internal/modules/esm/loader:318:18)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/module_job:80:40)
    at link (node:internal/modules/esm/module_job:78:36) {
  code: 'ERR_INVALID_URL_SCHEME'
}

Node.js v18.0.0
```
