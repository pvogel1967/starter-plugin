QBO UI Plugin Development
==================

These are instructions for getting started with QBO plugin development. Plugins are iFrames that you can insert into various places inside QBO.

Getting started with local development
-------

1. Fork this repo and rename it to the name of your plugin.
1. Clone the repo to your local machine
1. Open the server.crt file in the sslcert folder and add it to your keychain/trusted cert store (this will allow you to run your browser with full security turned on)
1. Add the following to your hosts file (/etc/hosts on *nix, mac, %WINDIR%\System32\drivers\etc\hosts on windows)

        127.0.0.1 localhost.<yourdomain>.com
        127.0.0.1 localhost.intuit.com 
   (the reason for the .intuit.com is the self-signed cert in this repository is set up for localhost.intuit.com, if you update the cert you can change the domain)
1. Edit package.json and replace "Starter Plugin" with your own plugin name and repository location
1. Run "npm install"
1. Run "grunt dev" for development on https://localhost.intuit.com:34212
1. A QBO Developer Sandbox account is recommended. Go to https://developer.intuit.com to get your free account.
1. After you create and log into your free sandbox account, go to this link https://sandbox.qbo.intuit.com/app/plugins/qbodeveloper
1. Click "Install" to install the qbo developer plugin
1. Visit the "Gear" menu and click "Company Settings". Find the Developer tab.
1. Add a new plugin with your own name (e.g. pavdemo). Notice it is marked "local storage". This means it will be configured on just your browser in its local storage.  It also defaults to work with this starter-bread's dev config from localhost.intuit.com, if you change the hostname and update the cert, change it here too.
1. Refresh the browser so it will load your configuration.
1. The example plugin overrides the Customers tab, so click the customers tab to see it. You may also access it from the Gear menu.

Access Points
-------

There are several places in QBO where you can create access points for your plugin (places where users can navigate to your plugin). To configure these, you edit the config.json file in your starter plugin. There are plenty of samples in that file.
