## 👋 Welcome to xorg 🚀  

xorg README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update xorg
```
  
## Install and run container
  
```shell
dockerHome="/var/lib/srv/$USER/docker/casjaysdevdocker/xorg/latest/volumes"
mkdir -p "$dockerHome"
git clone "https://github.com/dockermgr/xorg" "$HOME/.local/share/CasjaysDev/dockermgr/xorg"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/xorg/volumes/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-xorg-latest \
--hostname xorg \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/xorg:latest
```
  
## via docker-compose  
  
```yaml
services:
  ProjectName:
    image: casjaysdevdocker/xorg
    container_name: casjaysdevdocker-xorg
    environment:
      - TZ=America/New_York
      - HOSTNAME=xorg
    volumes:
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/xorg/latest/volumes/data:/data:z"
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/xorg/latest/volumes/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/xorg
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/xorg" "$HOME/Projects/github/casjaysdevdocker/xorg"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/xorg"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  

