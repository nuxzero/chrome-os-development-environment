Chrome-OS-Development-Environment
================================

This is tell you about "How to setup Chrome OS to the Developer machine?". I hope so mush this is will helpful for everyone interesting Chrome OS. Thank you.

# Open source shell
`shell`

# Download crouton from this link
http://goo.gl/fd3zc

# install debian
`sudo sh -e ~/Downloads/crouton -r wheezy -n debian -t cli-extra`

# Login
`sudo enter-chroot`

# Install apt-get
`sudo apt-get -f install`

# Setup LAMP
`sudo apt-get install mysql-server mysql-client phpmyadmin`

# Change root document directory
`sudo nano /etc/apache2/sites-available/default`
Change root document from `/var/www/` to `/home/{{username}}/local/Downloads/`
And restart apache `sudo service apache2 restart` or `sudo /etc/init.d/apache2 restart`
And `Sudo chmod 777 -R ~/Downloads`

# Install Laravel framework
- Install curl `curl -sS https://getcomposer.org/installer | php`
- Move composer `sudo mv composer.phar /etc/local/bin/`
- Create alias `alias composer='/usr/local/bin/composer.phar'`
- Create laravel project `composer create-project laravel/laravel your-project-name --prefer-dist`

# Error 'apache2 could not reliably determine the server's fully qualified domain name'
`sudo nano /etc/apache2/apache2.conf`
Add 'ServerName localhost'
And resert apache `sudo service apache2 restart`

# Fixing phpMyAdmin not found
Open apache2.conf `sudo nano /etc/apache2/apache2.conf`
And add 'Include /etc/phpmyadmin/apache.conf'

# Fixing phpMyAdmin login without password
Open phpmyadmin config `sudo nano /etc/phpmyadmin/config.inc.php`
Uncommend the line // $cfg['Servers'][$i]['AllowNoPassword'] = TRUE;

# Git installation
`sudo apt-get install git-core`

# Python installaion
`sudo apt-get install python`