Test project for comparing Ember.js and Backbone.js.

To serve these examples locally, you can create a local Apache vhost:

Add the following to '/etc/hosts'

   127.0.0.1       gg.local

Add the following to '/etc/apache2/extra/httpd-vhosts.conf':

   <VirtualHost *:80>
     ServerName gg.local
     DocumentRoot /path/to/genigames-test-ember
     <Directory /path/to/genigames-test-ember>
        AllowOverride all
        Options -MultiViews
     </Directory>
     
     ProxyPass        /biologica/ http://geniverse.dev.concord.org/biologica/
     ProxyPassReverse /biologica/ http://geniverse.dev.concord.org/biologica/
  
     ProxyPass        /resources/ http://geniverse.dev.concord.org/resources/ retry=1
     ProxyPassReverse /resources/ http://geniverse.dev.concord.org/resources/  
   </VirtualHost>

Restart Apache:

    $ sudo apachectl restart
   
   
Visit the Ember example at gg.local/ember/