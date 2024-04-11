FROM node:18-alpine
ENV PORT=80 
WORKDIR /app
COPY package*.json /app
RUN npm install
COPY . /app
EXPOSE $PORT
CMD [ "npm", "start"]