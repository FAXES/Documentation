# Creating Extensions

---

## Creating A Basic Extension

To create a extension you can use the following code example to get you started

```js
const config = require('../config.json'); // Original Config For Faxstore

const extConfig = {

}


module.exports = async function(app, connection, bot, faxstore) {
   // Code Here   
}
```

## Using Bot Commands

If you would like to create a extension that uses discord commands you may use this example


```js
const config = require('../config.json'); // Original Config For Faxstore

const extConfig = {

} // Config For Your Extension

module.exports = async function(app, connection, bot, faxstore) {

        let commands = [
            {
                name: "test",
                description: `test description`,
                options: [
                    {name: "test option", description: "test option description", type: "STRING", required: true}
                ]
            }
        ]
        commands.forEach(function(command) {
            bot.application.commands.create(command, config.discordConfig.guildId).catch(function(err) {console.log(err)});
        })

        bot.on("interactionCreate", async function(interaction) {
            if(interaction.commandName == "test") {
                
            }
            
    })
}
```