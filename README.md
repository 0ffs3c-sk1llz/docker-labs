# docker-labs

This project aims to gather some vulnerable machines by design or CTF challenges under docker machines. 

## Prerequisites

- Install docker-compose:

    curl -L https://github.com/docker/compose/releases/download/1.8.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose


- Create the bridge network

    docker network create --driver=bridge --subnet=10.10.10.0/24 ctf_nw

- Create the customized parent debian image

    docker build -t debian_custom ./base

## Create you containers

    docker-compose up
 
## Docker machines list

### DNS Bind 9

- a local DNS used to link containers together
- accessible from :
    - 10.10.10.2
    - dns.0ffs3c-sk1llz.com

### docker-flask

- a very simple poc flask app
- accessible at 
    - 10.10.10.3
    - flask.0ffs3c-sk1llz.com

### pwnedhub

- Docker of the pwnedhub vulnerable machin by design.
- The original project is available at https:// github.com/lanmaster53/pwnedhub/blob/master/LICENSE.txt
- accessible at 
    - 10.10.10.4:5000 
    - pwnedhub.0ffs3c-sk1llz.com:5000