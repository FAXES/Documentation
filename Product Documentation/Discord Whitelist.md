Hate updating those ACE Permission or database white-lists? Well just use Discord! DiscordWhitelist allows you to use a dynamic whitelist system based off of Discord roles.

This guide will assist you in setting up Discord Whitelist for your community. Follow it through and if you need assistance [contact us](https://weblutions.com/contact).

### Create Discord Bot
To operate DiscordWhitelist we need to have a Discord bot application in our guild. This bot doesn't need to be online, just in the guild.

1. First off, create an application on the [Discord developer portal](https://discord.com/developers/applications).
2. Click on 'Bot' on the **left navigation** bar and enable the bot. Fetch the bot token from this page and keep it handy for later.
3. Now in the 'General Information' tab copy the 'Client ID' and replace `CLIENT_ID_HERE` in the below template then navigate to that link.

```
https://discord.com/oauth2/authorize?client_id=CLIENT_ID_HERE&scope=bot&permissions=8
```

Now invite the bot into your guild.

### Installing DiscordWhitelist
Now we get to install the FiveM/RedM resource. This part must be followed correctly for the resource to work.

1. Download the whitelist from the [weblutions store](https://weblutions.com/releases/74).
2. Open the `config.js` file in the resource and edit to the your liking and save it.
3. Add `ensure DiscordWhitelist` into your server.cfg.

Takeaways, ensure to place your [license key](https://license.weblutions.com), Discord bot token, guild ID, and role IDs into the config. See the below example of the config.

```
var enableWhitelist = true;
var guildId = "358072894867111966"; 
var botToken = "TDWzMDE0ODIwMzQ5NjczNTZz.YDJJDg.TET4ro8l1IT0GA73PLgUGs4vU01";
var licenseKey = "CoWOtuE_zUmu1jW1FK9bJC0GECjA8uS4RncEUplolRUSJ";

var whitelistRoles = [
    "906061699562475581",
    "561341615759949834"
];
var blacklistRoles = [
    "ROLE_ID"
];

var notWhitelistedMessage = "You're Not Whitelisted. Please wait <<CACHE>> before trying again.";
var noGuildMessage = "Guild Not Detected. It seems you're not in the guild for this community.";
var blacklistMessage = "You're blacklisted from this server.";
var debugMode = false;
var cacheMaxTime = "2m";
```

Now everything should be ready to go! Still need help? Join our Discord if you haven't already.

![Invite](https://api.weblutions.com/discord/invite/faxes)
