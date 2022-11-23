# Creating Extensions

---

## Creating A Basic Extension

To create a extension you can use the following code example to get you started

```js
const config = require('../config.json'); // Original Config For Faxstore
const extConfig = require('./configs/EXTENSION_CONFIG.json'); // Extensions config

/*
	module.exports params:
	- app: ExpressJS application.
	- connection: MySQL connection
	- bot: Discord bot
	- faxstore: FaxStore event system
*/

module.exports = async function(app, connection, bot, faxstore) {
   console.log(`Extension started!`);
	
	app.get(`/myextension`, function(req, res) {
		res.send(`Here is a page running!`);
	});
}
```
