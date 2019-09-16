FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build


FROM nginx
EXPOSE port 3000
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPy --from=builder /app/build /usr/share/nginx/html