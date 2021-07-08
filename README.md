# Problem in frontend plugin

## Problem

I meet some problem when i use `@theia/generator-plugin` to generate a frontend hello-world plugin, and use `Host Plugin: start instance` to develop it, but it seems not work and i got this error in console.

```console
logger-protocol.ts:112 root ERROR Failed to load plugins: TypeError: __webpack_require__(...) is not a constructor
    at new PluginWorker (http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:14631:23)
    at HostedPluginSupport.push../node_modules/@theia/plugin-ext/lib/hosted/browser/hosted-plugin.js.HostedPluginSupport.initRpc (http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:1806:41)
    at HostedPluginSupport.<anonymous> (http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:1753:36)
    at step (http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:1203:23)
    at Object.next (http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:1184:53)
    at http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:1178:71
    at new Promise (<anonymous>)
    at push../node_modules/@theia/plugin-ext/lib/hosted/browser/hosted-plugin.js.__awaiter (http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:1174:12)
    at HostedPluginSupport.push../node_modules/@theia/plugin-ext/lib/hosted/browser/hosted-plugin.js.HostedPluginSupport.obtainManager (http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:1744:16)
    at http://localhost:3030/vendors-node_modules_theia_plugin-ext_lib_plugin-ext-frontend-module_js.bundle.js:1637:73
```

this problem is weird and i also encountered the same problem with the plug-in I developed before, it seem there is any conflict in webpack.

## How to reproduce

I am using Windows develop it, I haven't tried this problem will it occur in Linux.

`./theia/package.json` is my theia ide config file.

`./plugin` is generate by `@theia/generator-plugin`.

open theia and `Host Plugin: start instance` , this plugin not work and will have above error in console.