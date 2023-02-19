It's time to start configuring your site in the configuration file (`config.json`).

This section covers a variable documentation table on every single item inside the config file along with what it is and does as well as how to configure it.

### Discord Login
Although the most common Discord offers a range of out of app features which echo into the Discord platform that other services don't provide.

First things first, create a Discord application through the [Discord developer portal](https://discord.com/developers/applications)

Now on the OAuth2 page you will need to add the following as a redirect and replace the domain with yours. This is used in our login callback to actually log the user in.

```
https://example.com/auth/discord/callback
```
*Change `example.com` to represent your domain name.*

![discord1](https://faxes.zone/i/Giy35.gif)

Now, copy the Client ID and place it in the config file of FaxCad under the `tokens` section. Also copy the Client Secret from the Discord page into your FaxCad config.

---


Once you have configured FaxCad to have all of the **required** configuration options then you can proceed.

**[R]** symbols a required item.

---

| Variable Name     | Description                              | Type                                                                                              | 	Default Value            |
|-------------------|------------------------------------------|---------------------------------------------------------------------------------------------------|---------------------------|
| processPort       | The port that the application runs on    | [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) | `3000`                    |
| domain            | The domain which the CAD will operate on | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"http://localhost:3000"` |
| ownerId           | The Discord ID of the site owner         | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"DISCORD_ID_HERE"`       |
| discordBotToken   | Discord bot token                        | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"DISCORD_BOT_TOKEN"`     |
| oAuth2ClientId    | Discord OAuth2 client ID                 | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"DISCORD_CLIENT_ID"`     |
| oAuth2ClientToken | Discord OAuth2 client secret             | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"DISCORD_CLIENT_SECRET"` |
| faxesLicenseKey   | The license key to activate the software | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"FAXES_LICENSE_KEY"`     |
| host | The remote server to use. This should be an IP for a server or if it’s the machine then use `localhost` | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"localhost"` |
| username | The username used for the SQL login. | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"root"` |
| password | The password used for the SQL login. | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"password"` |
| database | The database name which contains the SQL tables. | [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) | `"faxcad"` |