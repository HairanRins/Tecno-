# Utiliser l'image officielle Nginx comme base
FROM nginx:alpine

# Supprimer le contenu par défaut de Nginx
RUN rm -rf /usr/share/nginx/html/*

# Copier les fichiers locaux vers le répertoire /usr/share/nginx/html du conteneur
COPY index.html /usr/share/nginx/html/index.html

# Exposer le port 80 (port par défaut pour HTTP)
EXPOSE 80

# Lancer Nginx en mode foreground
CMD ["nginx", "-g", "daemon off;"] 

