Configure system
================

add "127.0.0.1 localhost.mytrezor.com" to your HOSTS file

Build
================

```
sudo docker build --no-cache -t mytrezor_prod ./prod/
```

Run Production
==============

```
sudo docker run -p 8000:8000 -d mytrezor_prod grunt server
```

http://localhost.mytrezor.com:8000/
