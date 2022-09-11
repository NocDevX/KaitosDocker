FROM node:18-alpine

# Permite que as mudanças nos arquivos sejam observadas
ENV CHOKIDAR_USEPOLLING=true

WORKDIR /var/www

COPY kaitos .

RUN npm install

EXPOSE 3000