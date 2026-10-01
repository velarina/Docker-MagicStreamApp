#layer on docker file, this uses a lightweight Alpine Linux image with NodeJS 20 installed
#so we creating environment thats from an existing image
FROM node:20-alpine

#creating work dirrectory inside the container
WORKDIR /app

#install envsubst
RUN apk add --no-cache gettext

COPY package*.json ./
RUN npm install

#copy the rest of application file
COPY . .

#as before exposing port 8080 for the server container, here exposing 5173 for a container that will be derived from this image
EXPOSE 5173

#got command here for running react client
# CMD ["npm", "run", "dev", "--", "--host"]
#CMD ["npm", "run", "dev", "--", "--host"]
#generate env.js at runtime, then start dev server
CMD sh -c "envsubst < public/env.template.js > public/env.js && npm run dev -- --host"