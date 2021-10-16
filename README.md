# rationmela
To setup project locally:
1. Install xampp and run apache on 8081 and 4433 port.
2. Unzip codebase zip and save it under htdocs.
To enable it, open your httpd.conf file and uncomment the line

LoadModule filter_module modules/mod_filter.so

3. Access phpmyadmin, create DB name as bsuczxfi_rnmela and Import the sql file on phpmyadmin.

Changing php.ini at C:\xampp\php\php.ini

max_execution_time = 600
max_input_time = 600
memory_limit = 1024M
post_max_size = 1024M
Changing my.ini at C:\xampp\mysql\bin\my.ini

max_allowed_packet = 1024M



4. Access localhost:8081/rationmela to access the site locally.
5. In case of any product related issue, please update product with our attached csv file.


IN case if you're still facing issue, then please make sure that your .htaccess has correct configurations, for reference follow below:

php_value max_execution_time 300
        php_value max_input_time 180
        php_value max_input_vars 3000
        php_value memory_limit 2048M
        php_value post_max_size 2048M
        php_value session.gc_maxlifetime 1440
        php_value upload_max_filesize 2048M
		


RewriteEngine Off
RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
RewriteBase /
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]


<IfModule version.c>
  <IfModule filter_module.c>
    <IfVersion >= 2.4>
      FilterDeclare   COMPRESS
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'text/html'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'text/css'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'text/plain'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'text/xml'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'text/x-component'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'application/javascript'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'application/json'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'application/xml'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'application/xhtml+xml'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'application/rss+xml'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'application/atom+xml'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'application/vnd.ms-fontobject'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'image/svg+xml'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'image/x-icon'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'application/x-font-ttf'"
      FilterProvider  COMPRESS  DEFLATE "%{CONTENT_TYPE} = 'font/opentype'"
      FilterChain     COMPRESS
      FilterProtocol  COMPRESS  DEFLATE change=yes;byteranges=no
    </IfVersion>
    <IfVersion <= 2.2>
      FilterDeclare   COMPRESS
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/html
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/css
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/plain
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/xml
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $text/x-component
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/javascript
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/json
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/xml
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/xhtml+xml
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/rss+xml
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/atom+xml
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/vnd.ms-fontobject
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $image/svg+xml
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $image/x-icon
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $application/x-font-ttf
      FilterProvider  COMPRESS  DEFLATE resp=Content-Type $font/opentype
      FilterChain     COMPRESS
      FilterProtocol  COMPRESS  DEFLATE change=yes;byteranges=no
    </IfVersion>
  </IfModule>
  </IfModule>

# Remove browser bugs (only needed for really old browsers)
BrowserMatch ^Mozilla/4 gzip-only-text/html
BrowserMatch ^Mozilla/4\.0[678] no-gzip
BrowserMatch \bMSIE !no-gzip !gzip-only-text/html
Header append Vary User-Agent
# BEGIN ShortPixelWebp
# The directives (lines) between "BEGIN ShortPixelWebp" and "END ShortPixelWebp" are
# dynamically generated, and should only be modified via WordPress filters.
# Any changes to the directives between these markers will be overwritten.

# END ShortPixelWebp
