FROM node:16
# Installing libvips-dev for sharp Compatability
RUN apt-get update && apt-get install libvips-dev vim -y

# where our Strapi app will live
RUN mkdir -p /app

# Set /app as the working directory
WORKDIR /app

# Copy package.json and package-lock.json
# to the /app working directory
COPY ./backend/package*.json /app/

# Copy .env file
COPY ./.env /app/

ENV PATH /app/node_modules/.bin:$PATH

# Install dependencies in /app
RUN npm install

# Copy the rest of our Strapi folder into /app
COPY ./backend /app

EXPOSE 1337

# Build Strapi admin
RUN npm run build

# Run npm run develop, as we would via the command line 
CMD ["npm", "run", "develop"]