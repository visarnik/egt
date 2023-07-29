
FROM node:latest as build-stage
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . ./
RUN npm run build

# ready for production 
FROM node:latest
COPY --from=build-stage /app/build /myapp
EXPOSE 3000
ENTRYPOINT ["npm", "start"]