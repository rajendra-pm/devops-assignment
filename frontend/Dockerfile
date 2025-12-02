FROM node:18-alpine as build

WORKDIR /app

COPY package*.json ./
RUN npm install --legacy-peer-deps

# Fix auto ngcc lock forever issue
RUN rm -f /app/node_modules/.ngcc_lock_file
RUN npx ngcc --properties es2015 browser module main --first-only

COPY . .
RUN npm run build --prod

FROM nginx:1.25
COPY --from=build /app/dist /usr/share/nginx/html
