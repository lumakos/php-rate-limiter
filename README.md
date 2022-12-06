### PHP Rate Limiting with Redis
```
sudo apt update
sudo apt install -y php-redis
sudo systemctl restart apache2
```

Add a `rate-limiter.php` file in the root directory (/var/www/html/) of your web server. This file will be accessible to the public and users can type its address in a web browser to run it.

Hit:
```
curl -H "Accept: text/plain" -H "Content-Type: text/plain" -X GET http://localhost/rate-limiter.php?[1-5]
```
