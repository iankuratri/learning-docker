# base image is node alpine - lightest image of node available on docker hub
FROM node:18.12-alpine3.17

# creating a group and user name "app", then adding "app" user to "app" group,
# creating a user with less permission than root user, to restrict access to container file system in case of attack
# RUN addgroup app && adduser -S -G app app
# USER app

# setting (workdir) root dir of image to /app
WORKDIR /app

# creating a directory data, to be attached with docker volume
RUN mkdir data 

# copying package*.json files to image, so we can install dependencies before copying all the file, this helps in caching npm install step
COPY package*.json .

# installing dependencies
RUN npm install

# copyting all project files to image
COPY . .

# setting env variable
ENV API_URL=https://jsonplaceholder.typicode.com/

# exposing port 3000
EXPOSE 3000

# executing npm start command
CMD ["npm", "start"]