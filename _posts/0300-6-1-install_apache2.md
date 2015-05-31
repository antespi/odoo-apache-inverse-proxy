## Install Apache 2.4 in Ubuntu 14.04

### Default HTTP virtual host

{% highlight Bash %}
sudo nano /etc/apache2/sittes-available/default.conf
{% endhighlight %}

{% highlight ApacheConf linenos %}
<VirtualHost *:80>
   ServerAdmin webmaster@example.com
   ServerName odoo.example.com

   DocumentRoot /var/www/html

   <Directory /var/www/html>
      Options None
      AllowOverride None

      # RedirectMatch temp ^/(.*)$ http://otherhost.otherdomain.com

      # Access control by IP or IP range
      # Order deny,allow
      # Deny from all
      # Allow from 10.xx.0.0/16 127.0.0.0/255.0.0.0 ::1/128

      # Allow all
      Order allow,deny
      Allow from all
   </Directory>

   ErrorLog /var/log/apache2/default.error.log
   LogLevel warn

   CustomLog /var/log/apache2/default.access.log combined
</VirtualHost>
{% endhighlight %}

Download this file: [default.conf](files/default.conf)
