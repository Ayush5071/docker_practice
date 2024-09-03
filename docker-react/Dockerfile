#set the base image to create the image for react app
FROM node:20-alpine

#create a user with permission to run the app
# -S create a system user
# -G add the user to the group
# This is done to avoid running the app as root 

RUN addgroup app && adduser -S -G app app

USER app

WORKDIR /app

COPY package*.json ./

USER root

RUN chown -R app:app .

USER app

RUN npm install

COPY . .

EXPOSE 5173

CMD npm run dev