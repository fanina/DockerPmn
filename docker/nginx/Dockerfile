FROM nginx:1.17.8-alpine

RUN mkdir /gateway
WORKDIR /gateway

## Remove default nginx configs
RUN rm /etc/nginx/conf.d/default.conf
RUN rm /etc/nginx/conf.d/nginx.conf

## Copy custom configs from local to the nginx container
COPY ./nginx.conf /etc/nginx/conf.d
COPY ./default.conf /etc/nginx/conf.d

## Remove default nginx index page
RUN rm -rf /usr/share/nginx/html/*

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

EXPOSE 80

