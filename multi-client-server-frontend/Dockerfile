FROM node:13.12.0-alpine
WORKDIR /multi-client-server-frontend
ENV PATH /app/node_modules/.bin:$PATH
COPY package.json ./
COPY package-lock.json ./
RUN npm install
COPY . ./
RUN npm run build
CMD ["npm","run","start"]

# FROM nginx:stable-alpine
# COPY --from=build /multi-client-server-frontend/build /usr/share/nginx/html
# # new
# COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf
# EXPOSE 3000
# CMD ["nginx", "-g", "daemon off;"]
