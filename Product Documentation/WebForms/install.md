Installing WebForms is easy provided the guides are followed fully. Please take note of the below requirements for WebForms.

- Linux (Ubuntu) machine to operate. Commonly known as a VPS or dedicated box
- Domain Name
- Discord Account

<a href="https://linode.gvw92c.net/c/3604466/903982/10906" target="_blank" id="903982"><img src="https://weblutions.com/i/GSM2SG.png" border="0" alt="" width="728" height="90"/></a>

:::info
This is a Node.Js based website and requires a server to be ran. This will not run on common 'Shared Hosting' plans.
:::

### Step One

Complete the install of a LEMN stack if you have not done so before.

- [Install a LEMN Stack](/c/knowledgebase/lemn-stack-install)

### Step Two

Now upload your WebForms files into a new directory on the machine under `/home/webforms`.

Install the database by logging into MySQL.

:::info
Use `mysql -u root -p` to login to MySQL
:::

Now in MySQL run `source /home/webforms/installme.sql` to install the MySQL database.

Leave the MySQL console by using `exit`.

### Step Three

Edit the config.json file located at `/home/webforms/config.json`

Then open a new [screen session](https://docs.faxes.zone/c/knowledgebase/screen).

Now run the below commands to get WebForms started.

```
cd /home/webforms

npm install

node .
```

### Step Four
First things first, create a Discord application through the [Discord developer portal](https://discord.com/developers/applications)
Now on the OAuth2 page you will need to add the following as a redirect and replace the domain with yours. This is used in our login callback to actually log the user in.

```
https://example.com/auth/callback
```
*Change `example.com` to represent your domain name.*

Now, copy the Client ID and place it in the config file of WebForms under the `discord` section. Also copy the Client Secret from the Discord page into your Webforms config.

`oauthId` = Client ID
`oauthToken` = Client Secret

Save file. Completed.

### Step Five
To edit the site's logo or background you can find your WebForms root directory. Then navigate to `public/img/` and you can replace the files there! (Needs to be .png)!!

WebForms will now be started and running.
Go to your website & login with Discord. If you made yourself an admin in your `config.json` you should be able to access everything in the Staff section and edit as needed!
