FROM node:14.16.0-alpine3.13

RUN addgroup app && adduser -S -G app app
# creating directory `/app` using `root` user and changing its owner to `app` user and its group to `app` too
RUN mkdir /app && chown app:app /app
USER app

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . . 

EXPOSE 3001 

CMD ["npm", "start"]