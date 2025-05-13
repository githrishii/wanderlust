FROM node:21 AS Builder
WORKDIR /frontend
COPY package*.json ./
RUN npm i
COPY . .

FROM node:21-slim
WORKDIR /frontend
COPY --from=Builder /frontend .
COPY .env.sample .env.local

EXPOSE 3000

CMD ["npm","run","dev", "--","--host"]
