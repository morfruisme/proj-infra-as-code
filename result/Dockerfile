FROM node:18-slim

WORKDIR /usr/local/app
COPY package.json package-lock.json .
RUN npm install -g nodemon
RUN npm ci
RUN npm cache clean --force
RUN mv /usr/local/app/node_modules /node_modules

WORKDIR /
COPY --parents server.js views .
ENV PORT=8080
CMD ["node", "server.js"]
