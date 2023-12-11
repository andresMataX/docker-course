# /app /usr /lib
# FROM --platform=linux/amd64 node:19.2-alpine3.16
# FROM --platform=$BUILDPLATFORM node:19.2-alpine3.16
FROM node:19.2-alpine3.16

# cd app
WORKDIR /app

# dest /app
COPY package.json ./

# Instalar dependencias
RUN npm install

COPY . ./

# Realizar testing
RUN npm run test

# Eliminar archivos y directorios no necesarios
RUN rm -rf tests && rm -rf node_modules

# Unicamente dependencias de producción
RUN npm i --prod

# Comandos que se ejecutan cuando la imagen esté en un contenedor
CMD [ "node", "app.js" ]
