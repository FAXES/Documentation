Events are a great way to build and develop extensions in FaxTrack. Events are always being added and are documented here for your use in extensions or development of FaxTrack.


Using events is easy as pie, all you do is use the associated name and arguments. Here are some examples.

Listen for an event (on)
```js
faxtrack.on('projectCreated', function(userObject, projectObject) {
  // Do as you wish in the event, you can fetch data and even do other actions like make an automated webhook post.
  console.log(userObject);
  // userObject is the data passed in the users session (in an object), this will contain some login service data like their ID, avatar, and possibly guilds.
  console.log(projectObject);
  // This is an SQL object which contains the users database information.
});
```

## Events Dictionary

- **on** is a listen event that triggers with `faxstore.on()`
- **emit** is to emit an event to the system with `faxstore.emit()`

| Name                       | Arguments                                              | Description                                                                               | Type |
|----------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------|------|
| projectCreated | userObject, projectObject | Emits when a new project is created | on |
| projectEdited | userObject, projectObject | Emits when a project is edited | on |
| projectDeleted | userObject, projectObject | Emits when a project is deleted | on |
| issueCreated | userId, issueObject | Emits when an issue is created | on |
| issueSolved | userObject, solveObject, issueObject | Emits when an issue is marked as solved | on |
| issueDeleted | userObject, issueObject | Emits when an issue is deleted | on |
| issueComment | userObject, comment, issueObject | Emits when an issue is commented on | on |
| feedbackCreated | userId, feedbackObject | Emits when a feedback topic is created | on |
| feedbackSolved | userObject, solveObject, feedbackObject | Emits when a feedback topic is marked as solved | on |
| feedbackDeleted | userObject, feedbackObject | Emits when a feedback topic is deleted | on |
| feedbackComment | userObject, comment, feedbackObject | Emits when a feedback topic is commented on | on |

*[Improve this page](https://github.com/FAXES/Documentation/blob/main/Product%20Documentation/FaxTrack/FaxTrack%20Events.md)*
