Build Production
================

```
sudo docker build -t docker_prod ./prod/
```

Build Development
=================

```
sudo docker build -t --no-cache docker_dev ./dev/
```

Run Production
==============

```
sudo docker run -p 80:8000 -d docker_prod grunt server
```
http://ipaddress/

Run Development
===============

```
sudo docker run -p 8000:8000 -d docker_dev grunt server
```

http://localhost:8000/
