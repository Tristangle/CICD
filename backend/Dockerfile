# Utiliser l'image Python 3.12
FROM python:3.12

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers du projet
COPY . .

# Installer les dépendances
RUN pip install -r requirements/requirements.txt

# Donner les permissions d'exécution au script start.sh
RUN chmod +x start.sh

# Exposer le port 8000
EXPOSE 8000

# Exécuter le script de démarrage
CMD ["sh", "./start.sh"]
