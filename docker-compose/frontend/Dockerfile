FROM node:14.14.0 as builder
WORKDIR /frontend
COPY ./package.json .
RUN npm install
COPY . .
EXPOSE 3000
RUN npm run build
FROM nginx
EXPOSE 3000
COPY --from=builder /frontend/build /usr/share/nginx/html
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

