# Usar una imagen base de Node.js
FROM node:18-alpine

# Establecer el directorio de trabajo dentro del contenedor
WORKDIR /usr/src/app

# Copiar los archivos de definición de dependencias
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el código fuente
COPY . .

# El servicio de productos se ejecuta en el puerto 3002
EXPOSE 3002

# Comando para iniciar la aplicación
CMD [ "node", "index.js" ]