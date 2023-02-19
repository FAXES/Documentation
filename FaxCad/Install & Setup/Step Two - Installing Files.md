As FaxCAD uses Node.Js we want to use a proxy to direct users to the application through a manipulation method.

If you don't have a SFTP viewer take a look at [WinSCP](https://winscp.net/eng/index.php)


#### Nginx Configuration

Using a SFTP viewer navigate to `/etc/nginx/sites-available/default`. This is the Nginx site configuration. Delete the contents of the default file if you haven't made changes to it before.

Replace the contents with the below and change the `port` and `domain` as instructed.

```sh
server {
    
  server_name example.com; # Change domain to your domain
    
  location / {
    proxy_pass http://localhost:3000; # Change ONLY the port if needed.
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;
    proxy_set_header X-Real-IP $remote_addr;
  }
}
```

Once you have made your changes save the file and restart Nginx.

```
sudo systemctl restart nginx
```


#### Issue SSL Certificate

To issue our SSL certificate we want to run the below command and replace the domain name to ours.

```sh
sudo certbot --nginx -d example.com
```

You may be asked for some details like an email (this doesn't get used publicly).

When directed for a redirect method select the `2` option.


Now our certificate is issued we want to make sure it renews itself. Run the renew command to do so.

```sh
sudo certbot renew --dry-run
```

#### Installing FaxCAD Files

This might be the easiest step in the whole guide.

Using a SFTP application like WinSCP copy and paste the contents of our download to the `/home` directory.

We want to end location to be `/home/faxcad` so create a new directory if needed.

![winscpview](https://faxes.zone/i/ptEKA.png)


#### Installing The Database

Now, back to the harder stuff, it's time to install the MySQL database for FaxCAD .

Login to our MySQL server using the `mysql -u root -p` command and enter your password.

Next all we need to do once logged in is run the below command.


```sql
source /home/faxcad/installme.sql
```


#### Discord Application

As FaxCAD uses Discord as a login method along with popular logging and other enhanced features we will want to create a Discord Application in the [Discord Developer Portal](https://discord.com/developers/applications)

Create an application and add a bot profile.

![discordappcreate](https://faxes.zone/i/RUjze.gif)

In the Bot tab enable both gateway intents.