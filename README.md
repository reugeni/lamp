# lamp
Docker for LAMP projects with multiple php version sites

## Structure of folder

```
php74                # stack php 7.4
php81                # stack php 8.1
site1 --+            # 1st site
        +-- conf     # http config file
        +-- html     # your app source
site2 --+            # 2st site
        +-- conf     # http config file
        +-- html     # your app source
mysql                # store your database data
```

## Notes
- Clone/Edit sites(s) folder(s) and docker-compose.yml
- Create .env file based on dotenv.sample
- Create folder mysql to store your database data
