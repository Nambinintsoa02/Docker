Docker commande de base

1. Pour vérifie que Docker est installé et tourne:
```
docker --version
```
-Et pour vérifier si Docker tourne :
```
sudo systemctl status docker
```
-Pour le demarer
```
sudo systemctl start docker

```
-Voir les conteneurs en cours d’exécution
```
docker ps
```
- Voir les images Docker
```
docker images
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
 pour accéder à Portainer
 ```
 http://localhost:9000
```
