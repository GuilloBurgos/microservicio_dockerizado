# # Usar una imagen base de Node.js
# FROM node:18-alpine

# # Establecer el directorio de trabajo dentro del contenedor
# WORKDIR /usr/src/app

# # Copiar los archivos de definición de dependencias
# COPY package*.json ./

# # Instalar dependencias
# RUN npm install

# # Copiar el código fuente
# COPY . .

# # El servicio de usuarios se ejecuta en el puerto 3001
# EXPOSE 3001

# # Comando para iniciar la aplicación
# CMD [ "node", "index.js" ]

# # Dockerfile
# FROM node:18-alpine

# # Crear directorio de trabajo
# WORKDIR /app

# # Copiar package.json y package-lock.json
# COPY package*.json ./

# # Instalar dependencias
# RUN npm install

# # Copiar el resto del código
# COPY . .

# # Descargar script wait-for-it
# ADD https://raw.githubusercontent.com/vishnubob/wait-for-it/master/wait-for-it.sh /wait-for-it.sh
# RUN chmod +x /wait-for-it.sh

# # Exponer puerto
# EXPOSE 3001

# # Comando para esperar MySQL y luego iniciar el servicio
# CMD ["/wait-for-it.sh", "mysql:3306", "--", "node", "index.js"]

# FROM node:18-alpine

# WORKDIR /app

# COPY package*.json ./

# RUN npm install

# COPY . .

# # Instalar bash para wait-for-it
# RUN apk add --no-cache bash

# # Descargar script wait-for-it
# ADD https://raw.githubusercontent.com/vishnubob/wait-for-it/master/wait-for-it.sh /wait-for-it.sh
# RUN chmod +x /wait-for-it.sh

# EXPOSE 3001

# CMD ["/wait-for-it.sh", "mysql:3306", "--", "node", "index.js"]

FROM node:18-alpine

# Directorio de trabajo
WORKDIR /app

# Copiar archivos de dependencias
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el resto del código
COPY . .

# Exponer puerto
EXPOSE 3001

# Comando para esperar MySQL y luego iniciar el servicio
CMD sh -c "until nc -z mysql 3306; do echo 'Esperando MySQL...'; sleep 2; done; node index.js"