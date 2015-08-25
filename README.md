# wp-starter-kit

# configure wordpress cli

curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
chmod +x wp-cli.phar
sudo mv wp-cli.phar /usr/local/bin/wp

# configure bash profile to point to mamp instance of PHP

export MAMP_PHP=/Applications/MAMP/bin/php/php5.5.10/bin
export PATH="$MAMP_PHP:$PATH"
export PATH=$PATH:/Applications/MAMP/Library/bin/

# clone the repository into a directory

git@github.com:masonbraun/wp-starter-kit.git

cd wp-starter-kit
cd app

# download core wordpress files
wp core download

# create and setup the config file

wp core config --dbname=wpstarterkit --dbuser=root --dbpass=root --dbhost=localhost

wp db create

# install wordpress and setup database if fresh install

wp core install --url='http://wpstarterkit.dev' --title='WP Starter Kit' --admin_user=admin --admin_password=admin --admin_email='masonbraun@gmail.com'

# import an existing database, most likely scenario

wp db import wpstarterkit.sql

# export database

wp db export --add-drop-table

# update wordpress

wp core update

# install and activate plugins

wp plugin install advanced-custom-fields --activate
wp plugin install timber-library --activate
wp plugin install wp-migrate-db --activate





wp search-replace example.com newexample.com --dry-run
wp db import example_com.sql
wp db export

wp db export --add-drop-table

