Welcome to the License System installation guide. This guide assumes you have FaxStore operating and therefore have all [the requirements](https://docs.faxes.zone/c/faxstore/stepone#install-a-lemn-stack).


---

First off, unzip the contents into a new directory in `/home/licensesystem`. This is where the main installation contents will be.

Navigate to your Nginx sites configuration located in `/etc/nginx/sites-available`.

Open the file that's being used for FaxStore (likely the default file) and paste the below contents into it, make sure it's inserted below *all* existing content.

```
server {
  server_name example.com; # Change domain to yours.

  location / {
    proxy_pass http://localhost:3001; # Change the port if changed in the config file.
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;
    proxy_set_header X-Real-IP $remote_addr;
  }    
}
```


Now you must run the below to restart Nginx to have your changes work.

```
service nginx restart
```

You will also need to run Certbot to get your SSL certificate for your (sub)domain. Simply run this command with your domain included.

```
sudo certbot --nginx -d license.example.com
```

If using License System version 1.4.2 or above the SQL database information will automatically import for you. If not, import the data into the FaxStore database.

Now, edit your config file in your License System to your liking. Make sure the port and domain reflect what is located in the Nginx configuration.

> For logins to work on the License System, you may need to add additional URI redirects to each platforms settings as you did with FaxStore.


After that,

Create a [screen session](/c/knowledgebase/screen) with `screen -S license`

Once in your screen session we will want to navigate to the directory of our application. Use `cd /home/licensesystem`

We have one more important step before we start the License System. We must install the node modules.
Run the install command

```
npm install
```
This installs the required packages that help run the License System.

Now, it's time to start the License System. Use the basic start command with
```
node .
```

You're now done!
