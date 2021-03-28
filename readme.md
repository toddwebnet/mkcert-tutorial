# Notes:
======
## Introduction

Domain Used *.local.com
help: https://github.com/FiloSottile/mkcert

## Instructions
### add entry to hosts file
127.0.0.1 mkcert.local.com

### install mkcert on your host computer
brew install mkcert
brew install nss # if you use Firefox

for Linux
sudo apt install libnss3-tools


### allow mkcert to set itself up as a signing authority on our local machine
mkcert -install

### create cert
mkdir certs; cd certs
mkcert *.local.com



ok... so mkcert is pretty simple, but the best way to use it is by installing mkcert locally
# install it
brew install mkcert

# tell your local computer to trust mkcert
mkcert -install

# generate cert
mkcert *.domain.com

it generates a key and a cert file in whatever directory you are in

then in docker...
mount these via volumes
and tell nginx (or apache) to use those keys 
