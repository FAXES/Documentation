Creating your first extension is an easy process. All you need to do is create an extension file in the `extensions` folder. These files can only be in `.js` or `.sharf` file types.

*`.sharf` file extensions are private to Weblutions products and official extensions.*

Here is a little example of an extension.

```js
const config = require('../config.json'); // Original Config For Faxstore

/*
	module.exports params:
	- app: ExpressJS application.
	- connection: MySQL connection
	- bot: Discord bot
*/

module.exports = async function(app, connection, bot) {
	console.log(`Extension started!`);
	
	app.get(`/myextension`, function(req, res) {
		res.send(`Here is a page running!`);
	});
}
```

This registers a page under the /myextension link and simply shows the "Here is a page running!" text.
