# Node
FROM node:18-alpine

# Permite que as mudanças nos arquivos sejam observadas
ENV CHOKIDAR_USEPOLLING=true

# Define o diretório atual
WORKDIR /var/www

# Cria o volume e copia os arquivos do projeto
COPY kaitos .

# Dependências
RUN npm install

# Porta padrão
EXPOSE 3000