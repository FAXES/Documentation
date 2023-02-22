:::danger
This documentation is for when FaxCAD 1.2.2 is released.
:::

Events are a great way to build and develop extensions in FaxStore. Events are always being added and are documented here for your use in extensions or development of FaxCAD.

:::info
Suggest an event at the below link if you'd like to see a particular event
[Suggest new event](https://bugs.weblutions.com/projects/faxcad/add?t=feedback)
:::

Using events is easy as pie, all you do is use the associated name and arguments. Here are some examples.

Listen for an event (on)
```js
faxcad.on('onStart', function(licenseKey, siteDomain) {
  console.log(licenseKey);
  console.log(siteDomain);
});
```

Emit events (emit)
```js
const date = Date.now();
faxcad.emit('CreateAuditLog', 'UserID', 'Logged in', `logged in at <t:${date}>`);
```

## Events Dictionary

- **on** is a listen event that triggers with `faxcad.on()`
- **emit** is to emit an event to the system with `faxcad.emit()`

| Name                       | Arguments                                              | Description                                                                               | Type |
|----------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------|------|
| CreateAuditLog | action, note, userId | Generates an audit log. All arguments are required | emit |
| onStart | licenseKey, siteDomain | Emits when FaxCad first starts. | on |


*[Improve this page](https://github.com/FAXES/Documentation/blob/main/FaxCad/Events.md)*
