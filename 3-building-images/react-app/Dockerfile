FROM node:18.12-alpine3.17
# RUN addgroup app && adduser -S -G app app
# USER app
WORKDIR /app
COPY package*.json .
RUN npm install
COPY . .
ENV API_URL=https://jsonplaceholder.typicode.com/
EXPOSE 3000
CMD ["npm", "start"]