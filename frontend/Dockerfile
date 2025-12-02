FROM node:18-alpine as build

WORKDIR /app

# Copy only dependency files
COPY package*.json ./

# Install dependencies
RUN npm install --legacy-peer-deps

# Remove old ngcc lock if exists
RUN rm -f /app/node_modules/.ngcc_lock_file

# Manually run ngcc once
RUN npx ngcc --properties es2015 browser module main --first-only

# Copy your Angular source code (NOT including node_modules)
COPY . .

# Build the Angular app
RUN npm run build --prod

FROM nginx:1.25
COPY --from=build /app/dist /usr/share/nginx/html
