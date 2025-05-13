FROM node:21 AS Builder
WORKDIR /app
COPY package*.json ./
RUN npm i
COPY . .

FROM node:21-slim
WORKDIR /app
COPY --from=Builder /app .
COPY .env.sample .env.local

EXPOSE 3000

CMD ["npm","run","dev", "--","--host"]
