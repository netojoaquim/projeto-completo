# Etapa única: executa o React diretamente com Node
FROM node:20

# Define o diretório de trabalho
WORKDIR /app

# Copia apenas os arquivos de dependência primeiro
COPY package*.json ./

# Instala dependências
RUN npm install

# Copia o restante do projeto
COPY . .

# Expõe a porta padrão do React
EXPOSE 3000

# Inicia o React no modo de desenvolvimento
CMD ["npm", "start"]
