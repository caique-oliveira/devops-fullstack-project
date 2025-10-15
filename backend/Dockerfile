# ------------------------------
# Etapa 1 - Build da aplicação
# ------------------------------
FROM node:22-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install --production

COPY . .

# ------------------------------
# Etapa 2 - Execução
# ------------------------------
FROM node:22-alpine

WORKDIR /app

COPY --from=build /app /app

EXPOSE 5000

CMD ["node", "src/index.js"]
