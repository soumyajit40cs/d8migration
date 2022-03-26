# d8migration
drupal 8 user migration using migrate api.
Download "Migrate Source CSV" and enable it.
Download "Migrate Plus" and enable it
Download "Migrate Tools" and enable it.
Enable drupal migration related core modules
Ensure you're using the latest version of Drush.

Ref KB: https://www.drupal.org/docs/8/api/migrate-api/migrate-source-plugins/migrating-data-from-a-csv-source

for install drush -- composer require --dev drush/drush

if you want to delete user migration config file use this drush command : drush config-delete migrate_plus.migration.User_with_multiple_roles3 
#User_with_multiple_roles3 --> id of your configuration file

Fix this error Class &#039;League\Csv\Reader&#039; not found in Drupal\migrate_source_csv\Plugin\migrate\source\CSV->createReader() --->  composer require league/csv

rollback the changes : drush migrate:rollback User_with_multiple_roles

import migration : drush migrate:import User_with_multiple_roles

Note: "User_with_multiple_roles" id of your migrtion config file 

check migration status : drush ms
