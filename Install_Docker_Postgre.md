---
layout: page
title: "Install Postgresql on Docker"
permalink: /installpostgreondocker
---
Install_Docker_Postgre.md

# Redhat
Register https://www.redhat.com/wapps/ugc/register.html


# DOCKER

## Redhat registry

docker search registry.access.redhat.com/ubi

docker pull registry.access.redhat.com/rhel7:7.9-810.1665060344 --platform linux/amd64

## Docker create volume
docker volume create postgresql-vol

## Docker run command
docker run --name postgres --privileged -v `pwd`:/usr/product -w `pwd` -it 999a4bdb456e
docker run --name postgresRoboxes --privileged -v `pwd`:/usr/product -w `pwd` -it ee31eedcb74d
docker run --name postgresRocky --privileged -v `pwd`:/usr/product -w `pwd` -it 523ffac7fb2e

### Docker list images
docker images

### Docker remove images
docker rmi ee31eedcb74d -f

# Postgresql

## Install with image rhel 8 and the postgresql tar : Failed 
groupadd dba
useradd -g dba postgres -m -d /usr/product/pgsql
usermod -aG wheel postgres

subscription-manager register
subscription-manager register --username  --password  --auto-attach

tar xvfj postgresql-<version>.tar.bz2 $ 
cd postgresql-<version> $ 
./configure $ 
make 
make install

./configure -prefix=/usr/product/pgsql --with-pgport=12000

### Error 
configure:3966: error: in `/usr/product/postgres/distrib/postgresql-15.0':
configure:3968: error: no acceptable C compiler found in $PATH

 /usr/include/bits/local_lim.h:38:10: fatal error: linux/limits.h: No such file or directory
 #include <linux/limits.h>

yum install gcc-c++
