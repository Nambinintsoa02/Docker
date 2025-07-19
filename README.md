Docker commande de base

. Installer docker
```
apt update
apt install docker.io
```
. Pour vérifie que Docker est installé et tourne:
```
docker --version
```
. Et pour vérifier si Docker tourne :
```
sudo systemctl status docker
```
. Pour le demarer
```
sudo systemctl start docker

```
. Voir les conteneurs en cours d’exécution
```
docker ps
```
. Arreter un conteneur en cours
```
docker stop IDconteneur
```
. Voir tous les conteneurs (même arrêtés)
```
docker ps -a

```
. Voir les images Docker
```
docker images
```
. Supprimer une images
```
doker rmi NomImage
```
. Supprimer le conteneur actuel
```
sudo docker rm -f NomConteneur
```
-interface graphique pour gérer Docker :
```
docker volume create portainer_data
docker run -d -p 9000:9000 \
  --name=portainer \
  --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce
```
. Lancer une image
```
docker run -d -p 9000:9000 nomImage

```
 . Pour accéder à L'image
 ```
 http://localhost:9000
```



