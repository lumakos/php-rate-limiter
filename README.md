PHP Rate Limiting with Redis

sudo apt update
sudo apt install -y php-redis
sudo systemctl restart apache2

Hit:
curl -H "Accept: text/plain" -H "Content-Type: text/plain" -X GET http://localhost/php-limiter.php?[1-5]
