# Audiophile: Planning

#### Epicodus Capstone Project

#### _By Maggie Harrington_
##### _May 2017_



### Project Stages

##### To reach Minimum Viable Product (MVP):

* Set up basic blank Drupal site (see below under Creating Initial Project).

* Export database and include the .zip file in a db-backup folder within the sites directory (continue to update backup throughout project stages; periodically download backup from github and import to test backup).

* Create custom content types with fields listed:
  * Category:
    * Category Name
    * Notes
  * Manufacturer:
    * Manufacturer Name
    * Logo (photo)
    * Link
    * Notes
  * Product:
    * Product Name
    * SKU
    * UPC
    * Image
    * Description
    * Price
    * Weight (for shipping)
    * Dimensions (for shipping)
    * Inventory
    * Cost (unit amount paid by business for product)
    * Link
    * Notes
    * Manufacturer (linked to Manufacturer content type, one-to-many)
    * Category (linked to Category content type, many-to-many)
    * Recommended Products (linked field to other specified Products, many-to-many)


* Create relationships between content types using Entity Reference Module.

* Enter sample content.

* Create views for content using Views module.

* Enable e-commerce capabilities using Commerce and Stripe modules.

* Add business's logo and other personal info.

* Create custom theme based on specifications provided by business.


##### After MVP is complete:

* Add additional sorting options and/or views for products.

* Add search capabilities.

* Enter actual product content provided by business.

* Incorporate photos provided by business, possibly in a slideshow.

* Coordinate with business to configure e-commerce with existing accounts.

* Host site, preferably on business' existing host/domain.

* Make site live.

* Display 'Recommended Products' on individual product page.

* Additional styling/features as determined by business.

* Create user account for business with appropriate permissions to add/edit/delete product content.



### Setup/Installation Requirements (to clone existing project)

##### Requirements:

* MAMP (see https://www.mamp.info/en/downloads/ for installation details)

* Copy of the settings.php file (maintained separately)

##### Clone Project:

* Open the terminal and enter `cd Desktop`

* Enter `git clone ` and copy/paste the project link: https://github.com/maggie-harrington/capstone

* Enter `cd capstone`

* Copy settings.php into capstone/sites/default/


##### Import Database and Configure:

* In MAMP Preferences, change document root to project folder listed above. Make sure Apache Port is set to 8888 and MySQL Port is set to 8889.

* In your web browser, open phpMyAdmin: http://localhost:8888/MAMP/index.php?page=phpmyadmin&language=English

* Click the 'Import' tab, leave the default settings and make sure the character set is 'utf-8'.

* Click the 'Choose File' button next to 'Browse your computer' and navigate to capstone/sites/db-backup/audiophile.sql.zip , then click 'Go'.

* Select the 'Privileges' tab and click 'Add User', then enter username and password.

* Navigate to localhost:8888 in your web browser to view the project. (Make sure to keep the terminal window containing the server open while the project runs.)



### Creating Initial Project

* Download Drupal 7 core zip at https://www.drupal.org/project/drupal/releases/7.54

* Unzip and move to Desktop, rename project directory

* Edit .gitignore - remove `sites/*/files` line

* From within project directory:
`cp sites/default/default.settings.php sites/default/settings.php`
`chmod -R a+w sites/default`

##### MAMP:

* Change document root to project directory, Apache Port: '8888' and MySQL Port: '8889', 'start servers'

##### phpMyAdmin:

* 'Databases' > 'Create database' (database name: 'audiophile'; collation: 'utf8_general_ci') > 'Create'

* 'Privileges' > 'Add user' (username; password; host: select 'local') > 'Go'

##### Drupal Web Interface:

* localhost:8888/install.php

* 'Select an installation profile' (Standard') > 'Save and Continue'

* 'Choose language' ('English') > 'Save and Continue'

* 'Database configuration' (Database configuration: 'MySQL, MariaDB, or equivalent'; database name: 'audiophile'; username; password) > 'Advanced Options' (Database host: '127.0.0.1'; Database port: '8889') > 'Save and Continue'

* 'Configure Site' (Site name; e-mail) > 'Site Maintenance Account' (username; password) > 'Server Settings' (Default country; Default time zone) > 'Save and Continue'
