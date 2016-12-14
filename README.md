# Docker DevBox
A super simple docker devbox.

- Caddy http server
- PHP FPM
- MySQL

# Getting started.
Edit the values in `.env` and then run
```
$ docker-compose up
```

Obviously you'll need docker installed for this to work and make sure you enter the `DOMAIN` `.env` value as a host in your hosts file, point it to `127.0.0.1`

## Network Errors
If you're getting network errors when starting the box, edit the `IP_RANGE` value in your `.env` file to something else.

## MySQL
A MySQL db will be automatically created based on the value you enter in your `MYSQL_DATABASE` value in `.env`

## Rewrites
To rewrite requests to `index.php` add the following to your `Caddyfile` inside the site definition

```
rewrite {
    to {path} {path}/ /index.php?{query}
}
```
