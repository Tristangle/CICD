# Étape 1 : Construction du frontend
FROM node:18 as builder
WORKDIR /app

# Copier uniquement les fichiers de dépendances pour optimiser le cache
COPY package*.json ./
RUN npm ci

# Copier le reste du code et construire l'application
COPY . .
RUN npm run build

# Étape 2 : Servir le livrable
FROM nginx:alpine
# Copier le build (par défaut Vite génère un dossier "dist")
COPY --from=builder /app/dist /usr/share/nginx/html
# Exposer le port 80 (Nginx écoute sur ce port)
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
