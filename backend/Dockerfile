FROM node:18

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

EXPOSE 5000
ENV MONGO_URI=mongodb://mongo:27017/wanderlust
CMD ["npm", "start"]
