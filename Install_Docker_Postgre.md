---
layout: page
title: "Install Postgresql on Docker"
permalink: /installpostgreondocker
---
Install_Docker_Postgre.md

# DOCKER

## Redhat registry

docker search registry.access.redhat.com/ubi

docker pull registry.access.redhat.com/rhel7:7.9-810.1665060344 --platform linux/amd64

## Docker create volume
docker volume create postgresql-vol

## Docker run command
docker run --name postgres --privileged -v `pwd`:/usr/local -w `pwd` -it roboxes/rhel8 

### Docker list images
docker images

docker rmi ee31eedcb74d -f



# Postgresql

sudo dnf install -y https://download.postgresql.org/pub/repos/yum/reporpms/EL-8-x86_64/pgdg-redhat-repo-latest.noarch.rpm
sudo dnf -qy module disable postgresql
sudo dnf install -y postgresql15-server
sudo /usr/pgsql-15/bin/postgresql-15-setup initdb
sudo systemctl enable postgresql-15
sudo systemctl start postgresql-15