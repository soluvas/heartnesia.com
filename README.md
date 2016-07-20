# Heartnesia 2.x web app

Heartnesia 2.x web app is based on by Drupal 8.x with some of our own modules.

## Local Development

1. Install XAMPP
2. Edit Apache's php.ini and uncomment:

        extension=php_openssl.dll

3. Git clone under `C:/xampp/htdocs` folder
4. Composer install dependencies:

        composer -vvv install

5. Run Notepad as administrator, edit `C:\Windows\System32\drivers\etc\hosts` and append: (use your own local hostname)

        127.0.0.1	heartnesia.com.amanahwin

6. Edit `C:\xampp\apache\conf\extra\httpd-vhosts.conf` and append: (use your own local hostname)

        <VirtualHost *:80>
            ServerName heartnesia.com.amanahwin
            DocumentRoot "C:/xampp/htdocs/heartnesia.com"
            SetEnv APPLICATION_ENV "development"
            <Directory "C:/xampp/htdocs/heartnesia.com">
                DirectoryIndex index.php
                AllowOverride All
                Order allow,deny
                Allow from all
            </Directory>
        </VirtualHost>
