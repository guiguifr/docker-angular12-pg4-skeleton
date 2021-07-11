# Angular 12 requires Node 12.14.x/14.15.x or later minor.
FROM node:14
LABEL AUTHOR="Guillaume Delabre"

# Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions
# that follow it in the Dockerfile.
# Docker docs: https://docs.docker.com/engine/reference/builder/#workdir
WORKDIR /usr/src/app/app-ui

# Install version 12 of Angular.
RUN npm install -g @angular/cli@12

# Copy package*.json from HOST to the container (./ is the WORKDIR directory).
COPY /app-ui/package*.json ./

# Install all npm dependencies.
RUN npm install

# The package.json has been modified for this purpose including the "scripts" property.
CMD [ -d "node_modules" ] && npm run start || npm ci && npm run start
