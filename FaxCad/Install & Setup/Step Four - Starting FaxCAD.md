You've made it to the last step in the installation guide. This article is an easy one.

First off we want to create a license key at [license.faxes.zone](https://license.faxes.zone). Once you create a license key copy the key and place it in your config file.

After that,

Create a [screen session](/c/knowledgebase/screen) with `screen -S faxcad`

Once in your screen session we will want to navigate to the directory of our application. Use `cd /home/faxcad`

We have one more important step before we start FaxCAD... We must install the node modules.
Run the install command

```
npm install
```
This installs the required packages that help run FaxCAD.

Now, it's time to start FaxCAD. Use the basic start command with
```
node .
```

> 🎉 **Congratulations!** 🎉
FaxCad is now up and running. Please be sure to check out the guide on [using screen sessions](/c/knowledgebase/screen) for a more detailed guide on how you can control FaxCad.