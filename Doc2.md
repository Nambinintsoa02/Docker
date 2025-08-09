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
  tag image #Déclare l'image Docker pour créer un conteneur
  tag nom_conteneur #définir le nom du conteneur 
  tag networks #Permet de spécifier les réseaux à utiliser pour le conteneur

  tag build #Indique le chemin du Dockerfile pour l'image Docker.
  tag volumes #Définit les volumes partagés entre les conteneurs 
  tag ports #Lier les ports du conteneur aux ports de l'hôte
  tag version #Définit la version du fichier Docker Compose
```
