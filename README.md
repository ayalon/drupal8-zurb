## Usage

- git clone the repo
- run "composer install"
- set up a virtual host pointing to the web folder in apache/nginx

## Set the path to the drupal configuration

- in settings.php adapt the path to the config folder
```
$config_directories['sync'] = 'sites/default/config_migrate/sync';
```

## Do a site install with drush

Drush 8 ist required.

```
drush site-install config_installer \
--db-url=mysql://DBUSERNAME:DBPASSWORD@127.0.0.1/some_db \
--account-mail="admin@example.com" \
--account-name=admin \
--account-pass=some_admin_password \
--site-mail="admin@example.com" \
--site-name="Site-Install"
```

If you correctly set up the path in settings.php to the config folder, all settings will be imported during
the site install.

