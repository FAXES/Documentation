In 2.4.3 FaxStore will allow the registration of extensions. Stay tuned!

Registering extensions will allow editing settings of extensions along with reloading the extensions.

Here is a quick start, we'll be fully updating this at release.

```js
faxstore.registerExtension({
    name: 'File Uploader',
    config: extConfig,
    version: '1.1',
    author: 'FAXES',
    pages: [extConfig.StaffPath]
});
```

*Other options may be passed in the object. However 'name' is required.*
