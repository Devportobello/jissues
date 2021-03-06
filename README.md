## Requirements [![Build Status](https://travis-ci.org/joomla/jissues.png?branch=framework)](https://travis-ci.org/joomla/jissues)

The issue tracker application requires a server running:

* PHP 5.3.10 or later (Joomla Framework minimum version)
* MySQL 5.1 with InnoDB support

The application also has external dependencies installable via Composer.  You can run `ant installdep` if you have ANT installed or `composer update --dev` from the command line.

## Setup

1. Clone the git repo to where ever your test environment is located or download a ZIP file.
2. Copy `/etc/config.dist.json` to `/etc/config.json`.
3. Enter your database credentials in the `/etc/config.json` file.
4. Install dependencies from Composer by running `composer install` (or the equivalent for your system).  If you need to install Composer, you can do so from http://getcomposer.org/download/.
5. Install media files from Bower by running   `bower install`. If you need to install Bower you can do so by using NPM. Read more http://bower.io/.

From this point, you can setup your database in one of two ways:

*Preferred*

1. From a command prompt, run the script located at `cli/tracker.php` with the install option to set up your database.<br />`tracker.php install`

*Alternate*

If you are in an environment where you cannot execute PHP scripts from the command line, you can set up your database with the following steps:

1. Open `/etc/mysql.sql` and do a find/replace from `#__` to whatever your prefix is, and save.
2. Import the SQL into your database.

After setting up your database, verify the installation is successful by doing the following:

1. View the site in your browser to verify setup.
2. Open a console and execute cli/tracker.php with the `get` option to pull issues, issue comments and other information related to the project from GitHub.<br />
`cli/tracker.php get project`

See also: [CLI script](Documentation/CLI-script.md).

### Using Login with Github

If you want the 'login with Github' button to work properly you'll need to register an app with Github. To do this manage your account at github.com and go to the applications page. Create a new application.

You'll be asked for the application URL and the callback URL. This can be your test server or your localhost environment. As long as you enter the URL that your localhost app is running on. An example might be ```http://jissues.local```.

Once you've registered the app at Github you'll receive a ```Client ID``` and a ```Client Secret```, enter these into your JTracker ```config.json``` file, along with your Github login credentials. You should now be able to login with Github successfully

See also: [GitHub Authentication](Documentation/github-authentication.md)

### Virtual test environment

As an alternative method, there is a setup for a virtual test environment using Vagrant and VirtualBox.

See also: [Virtual server documentation](Documentation/virtual-test-server.md)

## Support & Discussion

* If you've found a bug, please report it to the Issue Tracker at https://github.com/joomla/jissues/issues.
* Please note this repository is _not_ for the Joomla CMS. Take all Joomla CMS issues, bug reports, etc.. to: http://github.com/joomla/joomla-cms
* For discussion about this project, please visit the Google+ Community at https://plus.google.com/u/0/communities/102541713885101375024.
