=== External Database Authentication Reloaded ===
Contributors: parkerj
Donate link: none
Tags: authentication, login, database, MySQL, MSSQL, PostgreSQL, SyBase, SQLite
Requires at least: 3.1
Tested up to: 4.2.2
Stable tag: 1.2.1

A plugin that allows the use of an external database (MySQL, PostgreSQL, MSSQL, and more) for authentication into WordPress.

== Description ==

*Please Note: When you update to version 1.2.1, you will need to re-enter the details on the settings page.*

This External DB Authentication plugin allows the use of an external MySQL, PostgreSQL, MSSQL, Sybase, Oracle, or SQLite database for authentication into WordPress.  It is required that you know the encryption method for the passwords stored in the external database. Password encryption methods include MD5, SHA1, plaintext, PHPass, or enter a custom hash/salt method.  It disables password reset/retrieval and account creation within the WordPress system on the user-end, and it doesn't allow updating from the WordPress end back into the external authentication source. 

In addition to authentication, the plugin allows you to:

* Choose additional fields, such as first name/last name and website, to be imported into WordPress.
* Enter a custom message for users concerning logins. 
* Do user role checks from the external database: you can set the plugin to check from a specific role field and compare to a value to allow login to WordPress.

== Installation ==

* Prepare your WP admin account on your external database: create an admin account in your external system.
* Change "New User Default Role" in Settings->General, if desired, to whatever level of control you wish external authenticated users to have.
* Upload `external-db-auth-reloaded` folder to the `/wp-content/plugins/` directory
* Activate the plugin through the 'Plugins' menu in WordPress
* Enter your external database settings in Settings->External DB settings

== Frequently Asked Questions ==

= My admin account for WP doesn't work anymore! =

We're authenticating externally, right?  Make sure the admin account username in the external source, matches the admin username in WordPress. Once it's in there you'll be able to log in as admin with no problems.  If you can't do this, delete the plugin and it'll restore access using your WP admin account.

= Can I still create accounts within WordPress? =

You could, but they don't work properly as it's only checking the external database for login accounts.

= Can I update user information within WordPress? =

No.

= My external database's passwords are hashed with a salt/datestamp/phases of the moon/etc =

Choose "Other" as your encoding method, then enter the method you use in the "Other" textbox as PHP code. If it involves more than the username and password, though, you may need to modify the plugin source code.

= I'm locked out! =

Delete or rename the plugin; if it's a DB connection-related error most likely you have the wrong connection, etc. information for the external database.

== Screenshots ==

1. Plugin config screen
2. Example login warning message upon access to wp-login.php
3. Example "Lost my password" retrieval attempt

== Changelog ==

= 1.2.1 (2015-05-28) =
* Added error logging; logs will be located in wp-content directory
* You will need to re-enter your settings after you upgrade to this version
* Now uses PDO for database connection
* Now supports MySQL, MSSQL, PostgreSQL, Sybase, Oracle and SQLite databases out of the box
* Plugin can now be translated into other languages

= 1.2.0 (2015-05-14) =
* Fixed mysqli database connection

= 1.1 (2013-01-15) =
* One setting wasn't registered
* Fixed issues with "Other" option encryption type
* Added SQL query for "Other" option encryption type
* Should now work with plaintext passwords

= 1.0 (2012-10-31) =
* Bug Fixes
* Updated Code
* Added the option to use PHPass as an encryption type