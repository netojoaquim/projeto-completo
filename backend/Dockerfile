# Etapa 1: build do projeto
FROM node:20 AS builder

# Define diretório de trabalho dentro do container
WORKDIR /app

# Copia arquivos de dependência
COPY package*.json ./

# Instala dependências
RUN npm install

# Copia o restante do código
COPY . .
COPY .env .env


# Compila o projeto Nest (gera dist/)
RUN npm run build

# Etapa 2: imagem de execução (mais leve)
FROM node:20-alpine

WORKDIR /app

# Copia apenas o resultado do build e dependências necessárias
COPY --from=builder /app/dist ./dist
COPY package*.json ./

# Instala apenas dependências de produção
RUN npm install --omit=dev

# Expõe a porta que o Nest usa
EXPOSE 5000

# Comando de inicialização
CMD ["node", "dist/main.js"]
