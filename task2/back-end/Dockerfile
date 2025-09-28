# Utiliser la dernière version d'Ubuntu comme image de base
FROM ubuntu:latest

# Mettre à jour APT et mettre à niveau les packages installés
RUN apt-get update && apt-get upgrade -y

# Installer Python3 et pip3
RUN apt-get install -y python3 python3-pip

# Supprimer le fichier EXTERNALLY-MANAGED s'il est présent
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Installer Flask à l'aide de pip3
RUN pip3 install Flask

# Copier le script API dans le conteneur
COPY api.py /opt/api.py

# Exposer le port sur lequel l'application s'exécutera
EXPOSE 5252

# Définir la commande pour exécuter le serveur Flask
CMD ["python3", "/opt/api.py"]
