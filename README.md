# wp-starter-kit

# download core wordpress files
wp core download

# create and setup the config file

wp core config --dbname=wpstarterkit --dbuser=root --dbpass=root --dbhost=localhost

wp db create

# install wordpress and setup database if fresh install

wp core install --url='http://wpstarterkit.dev' --title='WP Starter Kit' --admin_user=admin --admin_password=admin --admin_email='masonbraun@gmail.com'

# import and existing database, most likely scenario

# export database

wp search-replace example.com newexample.com --dry-run
wp db import example_com.sql
wp db export

wp db export --add-drop-table

