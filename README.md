# configuration-htaccess

``` console
  Options -Indexes

  RewriteEngine on

  # Allow POST and GET requests from your own system
  RewriteCond %{HTTP_REFERER} ^http://localhost/example/ [NC]
  RewriteCond %{REQUEST_METHOD} ^(POST|GET)$
  RewriteRule .* - [L]

  # Redirect all other requests to index.php
  RewriteCond %{REQUEST_METHOD} !^POST$
  RewriteCond %{REQUEST_URI} !^/index\.php$
  RewriteRule ^(.*)$ index.php?uri=$1 [QSA,L]
  
  ```
