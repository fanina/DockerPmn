FROM nginx:1.17.8-alpine

RUN mkdir /gateway
WORKDIR /gateway


RUN rm /etc/nginx/conf.d/default.conf
# RUN rm /etc/nginx/conf.d/nginx.conf

ADD ./docker/nginx/nginx.conf /etc/nginx/
ADD ./docker/nginx/default.conf /etc/nginx/conf.d

RUN rm -rf /usr/share/nginx/html/*

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

EXPOSE 80

