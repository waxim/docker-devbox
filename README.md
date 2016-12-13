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
If you're getting network errors on `dev_network` then open `docker-compose.yml` and replace all references for this value with another.

## Rewrites
To rewrite requests to `index.php` add the following to your `Caddyfile` inside the site definition

```
rewrite {
    to {path} {path}/ /index.php?{query}
}
```
