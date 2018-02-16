---
title: "Basic Installation"
_old_id: "32"
_old_uri: "2.x/getting-started/installation/basic-installation"
---

<div>- [Beginning Setup](#BasicInstallation-BeginningSetup)
  - [Installing MODX With An Existing Site](#BasicInstallation-InstallingMODXWithAnExistingSite)
      - [Existing Static HTML Site](#BasicInstallation-ExistingStaticHTMLSite)
      - [Existing Other CMS or ?Dynamically Driven Site](#BasicInstallation-ExistingOtherCMSor%EF%BB%BFDynamicallyDrivenSite)
  - [Pre-DNS Transfer Installation to Temporary Directory](#BasicInstallation-PreDNSTransferInstallationtoTemporaryDirectory)
- [Installing MODX Revolution](#BasicInstallation-InstallingMODXRevolution)
- [Install Options](#BasicInstallation-InstallOptions)
- [Database Options](#BasicInstallation-DatabaseOptions)
  - [Collations and Charsets](#BasicInstallation-CollationsandCharsets)
  - [Creating an Administrator User](#BasicInstallation-CreatinganAdministratorUser)
- [Pre-Installation Checks](#BasicInstallation-PreInstallationChecks)
- [Post-Installation Summary](#BasicInstallation-PostInstallationSummary)
- [Additional Info](#BasicInstallation-AdditionalInfo)
  - [WAMPServer 2.0i](#BasicInstallation-WAMPServer2.0i)
  - [MAMP on MacOSX](#BasicInstallation-MAMPonMacOSX)
  - [Debian](#BasicInstallation-Debian)
  - [Vista and XAMPP](#BasicInstallation-VistaandXAMPP)
  - [Installing Packages](#BasicInstallation-InstallingPackages)
  - [See Also](#BasicInstallation-SeeAlso)
 
</div>Beginning Setup
---------------

 After you've [downloaded](getting-started/installation "Installation") MODX Revolution, upload the .zip file to your server. On the server itself, either through your control panel extraction script or in the server's file manager, extract the file to its own directory. Copy or move all the files within the new extracted MODX version directory to the directory that you wish to install MODX into. You may delete the extracted folder and its contents, as well as the MODX .zip file once your installation is complete.

<div class="info"> You can install MODX into any directory you wish, although installing to the root is generally preferred for production sites. </div><div class="note"> FTP Warning - Using FTP to transfer unpacked files to your server may result in corrupted or incomplete transfers. This can affect your installation negatively. If at all possible, use your server's unpacking script or utility to transfer or move extracted MODX installation files. </div>### Installing MODX With An Existing Site

 Development sites often begin in a subdirectory, and then are [moved](administering-your-site/moving-your-site-to-a-new-server "Moving Your Site to a New Server") to the root directory when completed. The subdirectory method is useful if you've got an existing site that must remain available during development, or for subdomain MODX installations. It is also possible to leave MODX in a subdirectory and use .htaccess to rewrite your urls to the root.

#### Existing Static HTML Site

 If your existing site is static html with an index.html or similar start page, you can install MODX into the root folder alongside your static site while developing. When you are ready to go live, rename or move your static html files and MODX will take over. **Do not enable** [Friendly URL's](administering-your-site/using-friendly-urls "Using Friendly URLs") if using this method until after your html files have been moved or renamed. As always, **back up your existing site** prior to installing MODX Revolution or making any changes to your current file structure.

#### Existing Other CMS or Dynamically Driven Site

 Do not install MODX Revolution into a directory that contains another dynamically driven site or CMS until that site is removed. Use the subdirectory method to develop MODX in this case.

<div class="info"> In all cases except for a new blank site, installing MODX Revolution to a subdirectory for development is the safest method. </div>### Pre-DNS Transfer Installation to Temporary Directory

 If your host provides a temporary installation folder to develop in prior to DNS transfer, once your DNS has been transferred you will need to reference the [Moving Your Site to Another Server](administering-your-site/moving-your-site-to-a-new-server "Moving Your Site to a New Server") page and update the configuration files: _core/config/config.inc.php, /config.core.php, /connectors/config.php, and /manager/config.core.php_ paths to point to your new root directory.

Installing MODX Revolution
--------------------------

 Start the install process by loading your web browser and running the setup script by navigating to the **setup/** folder.

<div class="info"> You might want to check the [Server Requirements](getting-started/server-requirements "Server Requirements") page first. If you're still having issues installing, please read the [Troubleshooting Installation](getting-started/installation/troubleshooting-installation "Troubleshooting Installation") page. </div><div class="note"> Before running setup, make sure your core/cache/ and core/config/ directories are writable by PHP. </div> From there you will be asked to choose a language, and be presented with a welcome screen. Click Next when you're ready.

Install Options
---------------

 After this, you'll be presented with a screen with some Install Options:

 ![](/download/attachments/18678053/setup-opt1.png?version=2&modificationDate=1280259765000)

 The New Installation option should be the only available option for you to choose. If you need to adjust the file permissions for your webserver, you can do so in the textfields below. Most servers will be fine with the default values.

 When you're finished, click Next to proceed.

Database Options
----------------

 From here, you will get a form asking you for your database information:

 ![](/download/attachments/18678053/setup-db-1.png?version=1&modificationDate=1306342492000)

<div class="note"> You can create your database and user prior to this step. Make sure your database user is associated with the new database and the user is given permission for all privileges for that database. </div>- Add in your database hostname, which is the URL at which your database is located. For most users, this will be 'localhost'.
- Enter your database user name. On some hosts, your database username is prefixed with the site owner directory name such as siteOwner\_modxDatabase. In this case, the entire database name must be entered. Check your database tool in your control panel, or the database itself for such a prefix.
- Your username may also be prefixed with the same site owner directory name. If so, you must prefix your username here the same. i.e. siteOwner\_databaseUserName.
- Enter your password.
- Also, if you want, you can specify a different table prefix here. This tells MODX to prefix the tables with this value - this is useful should you want to make multiple MODX installations on one database.
- When finished, click the 'Test database server connection and view collations' link. Should you have any errors, they will show below. If you do have errors, check to make sure your database username and password are correct. Also, if your user does not have access to create a database, you might need to do that manually.

<div class="info"> **MySQL Notes**   
 If you have your MySQL server on a different port, specify it like so: "my.database.com;port=3307", with the ;port= appending the IP/hostname.  If you are running your MySQL server with networking disabled, you can specify the socket name like this: ";unix\_socket=MySQL".

 </div><div class="info"> **Microsoft SQL Server Notes**   
 Support for Microsoft SQL Server was introduced in MODX Revolution 2.1  Depending on your SQL Server's network configuration, there are different ways you may specify your host.

- Named pipe: (local)/SQLEXPRESS
- Tcp/ip: 127.0.0.1,2301 (IP, port)

 Due to the way that the PDO driver for SqlSrv works, you may not get an error message or a response back after clicking 'Test database server connection and view collations'. If this happens, it is an indication that there is a problem connecting to the database, authenticating or selecting the database itself. After verifying your settings, click the Back button to go to the previous page, and then Next to get back to the Database Options page.

 </div>### Collations and Charsets

 This will then popup another form for setting your database charset and collation:

 ![](/download/attachments/18678053/setup-db2.png?version=1&modificationDate=1280264244000)

 For most users you can leave these values at what they are. However, if you need to change them, **make sure** the collation matches the charset. Click the 'Create or test selection of your database.' after you've finished.

<div class="info"> **Microsoft SQL Server Notes**   
 MODX has only been tested with SQL Server's Latin1 character set. </div>### Creating an Administrator User

 ![](/download/attachments/18678053/setup-db3.png?version=1&modificationDate=1280264231000)

 This form will now present you with a few fields for setting up your administrator user. Specify a username that you want to be the administrator username.

<div class="note"> MODX recommends **not** using 'admin', as this is a common administrator username and is often the first username hackers check. </div> From there, put in your email (or the email of your administrator) and specify a password. Click next when you're finished.

<div class="info"> Some host's server configurations won't allow MODX to send emails if the System Setting [emailsender](https://rtfm.modx.com/revolution/2.x/administering-your-site/settings/system-settings/emailsender) (set at install to the email address entered for the default admin user) is not valid for the domain. If MODX is not sending registration or form emails, check the [emailsender](https://rtfm.modx.com/revolution/2.x/administering-your-site/settings/system-settings/emailsender) and set it to a valid email address for the hosted domain.  
</div>Pre-Installation Checks
-----------------------

 MODX will then proceed with a list of checks to verify that your system is ready for installing. If any of these fail, you'll need to proceed with the directions that it suggests to make sure your environment meets the [Server Requirements](getting-started/server-requirements "Server Requirements") and has the correct directories writable.

 Once you're ready, and all the checks pass, click 'Install' to proceed.

<div class="note"> If you get a blank screen or cannot proceed after clicking 'Install', verify these steps: 1. Make sure the directories "/core/packages","/core/cache", "/core/import", and "/core/export" are writable.
2. Make sure your php.ini setting sets memory\_limit to 128M, and max\_execution\_time to 120
3. Create a blank file "/core/config/config.inc.php" and make it writable. **DO NOT COPY config.inc.tpl! Just make it a blank file!**
4. Post a message in the [Revolution forum](http://modxcms.com/forums/index.php/board,280.0.html) regarding your issue. State your server setup and installation info, and we'll try and help you find a solution.
 
</div>Post-Installation Summary
-------------------------

 MODX will then let you know if any errors occurred during install, and prompt you to attempt reinstallation should any of those errors have occurred.

 When install is successful, click 'Next' to proceed, and you'll be presented with one final option:

 ![](/download/attachments/18678053/setup-cleanup1.png?version=1&modificationDate=1280264548000)

 MODX recommends that you make sure to remove the setup/ directory after installing, to safeguard your site from anyone else trying to run setup on your site. You can do this by clicking the 'Check this to DELETE the setup directory from the filesystem.' checkbox.

<div class="note">WARNING: the setup application grants powerful and far-reaching control over your server. DO NOT leave it in place, after you've finished installing MODX.

 </div> When ready, click 'Login' to be presented with the Login form for the manager interface. You're finished!

Additional Info
---------------

 Some other special cases:

### WAMPServer 2.0i

 Please see this article: [Problems with WAMPServer 2.0i](getting-started/installation/basic-installation/problems-with-wampserver-2.0i "Problems with WAMPServer 2.0i")

### MAMP on MacOSX

 MAMP (including latest 1.8.4) works fine with MODX Revolution, with one exception. You cannot use eAccelerator as the caching system, as the drivers compiled with MAMP are faulty with regards to PDO and will cause Apache kernel errors. Select the 'xCache' caching drivers to remedy this.

### Debian

 Debian uses outdated MySQL drivers for its PHP build that will need to be updated; please see the [MODX Revolution on Debian](getting-started/installation/basic-installation/modx-revolution-on-debian "MODX Revolution on Debian") article for more information.

### Vista and XAMPP

 There have been reported problems with installing Revolution on 64-bit Vista with XAMPP. We cannot guarantee a working solution on that OS and setup at this time.

<div class="note"> Some users have reported that applying a fix found here: <http://www.apachefriends.org/f/viewtopic.php?f=16&t=32617> will fix Apache crashing errors with PDO support in XAMPP. </div>### Installing Packages

 For information on installing 3rd-party packages, see the [How to Install Packages](developing-in-modx/advanced-development/package-management "Package Management") article.

### See Also

1. [MODX Revolution on Debian](getting-started/installation/basic-installation/modx-revolution-on-debian)
2. [Lighttpd Guide](getting-started/installation/basic-installation/lighttpd-guide)
3. [Problems with WAMPServer 2.0i](getting-started/installation/basic-installation/problems-with-wampserver-2.0i)
4. [Installation on a server running ModSecurity](getting-started/installation/basic-installation/installation-on-a-server-running-modsecurity)
5. [MODX and Suhosin](getting-started/installation/basic-installation/modx-and-suhosin)
6. [Nginx Server Config](getting-started/installation/basic-installation/nginx-server-config)
7. [YouTube video by a MODX Ambassador](http://www.youtube.com/watch?v=Wwrq-3CWFVU)