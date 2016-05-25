README
===============

A simple Textpattern set-up.

## Setup

### Config

Create a new file with Textpattern config from initial `docker-compose up`...

```bash
docker cp config.php txp-web:/var/www/html/textpattern/
```

Set correct timezone for PHP:

```
docker cp php.ini txp-web:/usr/local/etc/php/php.ini
```

### Remove setup Directory

```
docker exec txp-web rm -rd /var/www/html/textpattern/setup
```

## Importing a Database

`docker exec -i txp-db mysql -u root -ptxproot txp < BACKUP/filtxp.sql`

## Copy Additional files and images

For example, from backup:

```bash
docker cp BACKUP/files txp-web:/var/www/html/
docker cp BACKUP/images txp-web:/var/www/html/
```