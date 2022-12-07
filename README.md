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

### Understand the problem and establish design scope
Q: What kind of rate limiter are we going to design? Is it a client-side rate limiter or server-side API rate limiter?

A: Great question. We focus on the server-side API rate limiter.

Q: Does the rate limiter throttle API requests based on IP, the user ID, or other properties?

A: The rate limiter should be flexible enough to support different sets of throttle rules.

Q: What is the scale of the system? Is it built for a startup or a big company with a large user base?

A: The system must be able to handle a large number of requests.

Q: Will the system work in a distributed environment?

A: Yes.

Q: Is the rate limiter a separate service or should it be implemented in application code?Interviewer: It is a design decisio up to you.

Q: Do we need to inform users who are throttled?

A: Yes.
