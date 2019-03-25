# TEAMPASS containers

start containers
```
docker-compose build && docker-compose up -d
```

clone src
```
git clone https://github.com/nilsteampassnet/TeamPass.git teampass-data
```

fix permissions:
```
chown -R 65534:65534 ./teampass-data
```

goto url
```
http://localhost
```


