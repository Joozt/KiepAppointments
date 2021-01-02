Forked from [easyappointments.org](https://easyappointments.org) and simplified.

## Setup
On Windows
 - Install Git with Git Bash https://gitforwindows.org/
 - Install NPM https://www.npmjs.com/
 - Install PHP 7.4 https://windows.php.net/download#php-7.4
 - Enable GD2 plugin in php.ini
 - Install Composer https://getcomposer.org/download/
 - Install Docker https://hub.docker.com/editions/community/docker-ce-desktop-windows/
 
```
git clone https://github.com/Joozt/KiepAppointments.git
cd KiepAppointments
npm install
composer update
composer install
npm start
```

## Build
```
npm run build
```

## Installation
 - Upload the build directory to the server
 - Make the `storage` directory writable
 - Rename "config-sample.php" to "config.php" and update its contents based on your environment
 - Follow installation guide


## Run PHP & MySQL Docker
Change `config.php` to:
```php 
class Config {
    // ------------------------------------------------------------------------
    // GENERAL SETTINGS
    // ------------------------------------------------------------------------
    
    const BASE_URL      = 'http://localhost:8000'; 
    const LANGUAGE      = 'dutch';
    const DEBUG_MODE    = TRUE;

    // ------------------------------------------------------------------------
    // DATABASE SETTINGS
    // ------------------------------------------------------------------------
    
    const DB_HOST       = 'easyappointments-database:3306';
    const DB_NAME       = 'easyappointments';
    const DB_USERNAME   = 'root';
    const DB_PASSWORD   = 'root';

    // ------------------------------------------------------------------------
    // GOOGLE CALENDAR SYNC
    // ------------------------------------------------------------------------
    
    const GOOGLE_SYNC_FEATURE   = FALSE; // You can optionally enable the Google Sync feature. 
    const GOOGLE_PRODUCT_NAME   = '';
    const GOOGLE_CLIENT_ID      = '';
    const GOOGLE_CLIENT_SECRET  = '';
    const GOOGLE_API_KEY        = '';
}
```

```
cd docker
docker-compose up
```
In the host machine the server is accessible from `http://localhost:8000` and the database from `localhost:8001`.  