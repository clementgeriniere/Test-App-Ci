# Utilisez une image de base contenant Node.js
FROM node:10-alpine

# Mettez à jour les paquets et installez les outils nécessaires
RUN apk update && \
    apk add --no-cache bash git openssh

# Définissez le répertoire de travail à l'intérieur de l'image
WORKDIR /app

# Copiez les fichiers package.json et package-lock.json dans l'image
COPY package*.json ./

RUN apk add --no-cache python2 g++ make

# Installez les dépendances du projet
RUN yarn

# Copiez tous les fichiers du répertoire actuel dans l'image
COPY . .

# Définissez le port sur lequel le serveur Angular sera exposé
EXPOSE 4200

# Démarrez l'application Angular
CMD ["npm", "start"]
