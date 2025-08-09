
.Telecharge une images depuis un registre (par defaut :docker hub) latest version
```
docker pull nom_images
```


#Utilisation tag

.Télécharger une image Docker avec le tag spécifié.
```
docker pull nom_image:tag
docker pull ubuntu:22.04
```
.fichier compose.yml
```
tag service: #Définit les conteneurs et leurs configurations
```
```
  tag image #Déclare l'image Docker pour créer un conteneur
```
```
  tag nom_conteneur #définir le nom du conteneur
```
```
  tag networks #Permet de spécifier les réseaux à utiliser pour le conteneur
```
```

  tag build #Indique le chemin du Dockerfile pour l'image Docker.
```
```
  tag volumes #Définit les volumes partagés entre les conteneurs
```
```
  tag ports #Lier les ports du conteneur aux ports de l'hôte
```
```
  tag version #Définit la version du fichier Docker Compose
```
.Escemple:
```
version: '3.8'  #tag version

services: #tag services
  web:
    image: nginx:1.25  tag image
    container_name: mon_nginx  # tag conteneur_name
    ports:  #  tag ports
      - "8080:80"
    volumes:  #tag  Volume
      - ./site:/usr/share/nginx/html
    networks:  #  tag networks
      - mon_reseau

  app:
    build: ./app  : #tag build
    container_name: mon_app
    ports:
      - "5000:5000"
    volumes:
      - ./app_data:/data
    networks:
      - mon_reseau

networks:  #  tag networks
  mon_reseau:

volumes:  # Définition des volumes nommés (facultatif ici)
  app_data:
```


#Docker file
```
FROM : Image de base
FROM python:3.11-slim

RUN : Exécuter des commandes lors de la construction
RUN apt-get update && \
    apt-get install -y curl && \
    pip install flask

COPY : Copier les fichiers locaux vers l'image
COPY app.py /app/app.py

# Définir le répertoire de travail
WORKDIR /app

ENTRYPOINT : Commande principale qui sera toujours exécutée
ENTRYPOINT ["python"]

CMD : Définit la commande par défaut à exécuter lorsque le conteneur démarre.
CMD ["app.py"]
```


#Utilisation de docker stack

Déployer une pile de services dans une cluster docker swarm
```
docker stack deploy
```
Supprimer une pile de services dans docker swarn
```
docker stack rm
```


#Utilisation de docker compose

.Affiche le service
```
docker compose ls
```
```
docker compose up -d
```
.Arreter tous les conteneur
```
docker compose down
```
