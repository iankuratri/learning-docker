FROM node:18.12-alpine3.17
WORKDIR /app
COPY . .
RUN npm install
ENV API_URL=https://jsonplaceholder.typicode.com/
EXPOSE 3000
RUN addgroup app && adduser -S -G app app
USER app