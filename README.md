Build Development
=================

```
sudo docker build --no-cache -t mytrezor_dev ./dev/
```

Run Development
===============

```
sudo docker run -p 8000:8000 -it mytrezor_dev grunt server
```

http://localhost:8000/

Build Production
================

```
# Edit Dockerfile with your hosting DNS
# in _TWO_ places in the /prod/Dockerfile replace "mytrezor.com" with your domain
sudo docker build --no-cache -t mytrezor_prod ./prod/
```

Run Production
==============

```
sudo docker run -p 80:9000 -d mytrezor_prod grunt server
```

http://YOURDOMAIN.COM/
