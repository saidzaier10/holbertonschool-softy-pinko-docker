# Utiliser la dernière version d'Ubuntu comme image de base
FROM ubuntu:latest

# Mettre à jour les listes de paquets APT
RUN apt-get update

# Mettre à jour tous les logiciels installés
RUN apt-get upgrade -y

# Installer Python3 et pip3
RUN apt-get install -y python3 python3-pip

# Si tu rencontres l'erreur 'This environment is externally managed'
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Installer Flask et flask-cors avec pip3
RUN pip3 install flask
RUN pip3 install flask-cors

# Définir /app comme répertoire de travail
WORKDIR /app

# Copier le fichier Python 'api.py' dans le répertoire de travail
COPY ./api.py /app/api.py

# Exécuter l'application Flask lorsque le conteneur démarre
CMD ["python3", "api.py"]
