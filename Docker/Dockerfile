
FROM node:latest as build-stage
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . ./
RUN npm run build

# ready for production
FROM node:latest
WORKDIR /myapp
COPY --from=build-stage /app /myapp
EXPOSE 3000
CMD ["npm", "start"]