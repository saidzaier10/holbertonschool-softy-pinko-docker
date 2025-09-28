# Utiliser l'image de base Nginx
FROM nginx:latest

# Copier les fichiers du front-end dans le répertoire d'hébergement de Nginx
COPY ./softy-pinko-front-end /var/www/html/softy-pinko-front-end

# Copier la configuration Nginx personnalisée dans le conteneur
COPY ./softy-pinko-front-end.conf /etc/nginx/conf.d/default.conf
