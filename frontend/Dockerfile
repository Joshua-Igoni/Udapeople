FROM node:16.13.2 as build
# Add a work directory
WORKDIR /app
# Cache and Install dependencies
COPY package.json package.json
COPY package-lock.json package-lock.json 
# Install app dependencies
RUN npm ci --production
# Copy app files
COPY . .
# Build the app
RUN npm run build

FROM nginx:1.12-alpine

COPY --from=build /app/build /usr/share/nginx/html
# Expose port
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]