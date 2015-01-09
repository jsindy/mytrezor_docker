Build Development
=================

```
sudo docker build --no-cache -t docker_dev ./dev/
```

Run Development
===============

```
sudo docker run -p 8000:8000 -d docker_dev grunt server
```

http://localhost:8000/

Build Production
================

```
# Edit Dockerfile with your hosting DNS
# in _TWO_ places in the /prod/Dockerfile replace "localhost.mytrezor.com" with your domain
sudo docker build -t docker_prod ./prod/
```

Run Production
==============

```
sudo docker run -p 80:8000 -d docker_prod grunt server
```

http://YOURDOMAIN.COM/
