# Usar una imagen base de Node.js
FROM node:18-alpine

# Establecer el directorio de trabajo dentro del contenedor
WORKDIR /usr/src/app

# Copiar los archivos de definición de dependencias
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el código fuente de la aplicación al directorio de trabajo
COPY . .

# El API Gateway se ejecuta en el puerto 3000
EXPOSE 3000

# Comando para iniciar la aplicación
CMD [ "node", "index.js" ]