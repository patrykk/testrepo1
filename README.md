## Example HAProxy SSL setup


run:

```
docker-compose build
docker-compose up -d 


or:
docker-compose up --force-recreate --build -d

```

stop:
```
docker-compose stop 
docker-compose rm
```

gen keys:
```
openssl genrsa -out web.key 2048
openssl req -subj "/C=PL/ST=Wroclaw/L=Dolnyslask/O=Kowalczyk/OU=IT/CN=kowalczyk.xyz/emailAddress=patryk@kowalczyk.xyz" -key web.key -new -out web.csr
openssl x509 -req -days 730 -in web.csr -signkey web.key -out web.crt 2>/dev/null
cat web.crt > web.pem
cat web.key >> web.pem
```

To hit the server, go to:

https://a.b.c.d

Where `a.b.c.d` is your docker/boot2docker IP. You'll get some warnings about
self-signed certificates, but this is OK