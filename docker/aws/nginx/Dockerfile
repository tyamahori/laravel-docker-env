FROM nginx:1.17.9

COPY ./laravel/public/index.php /opt/laravel/public/index.php
COPY ./laravel/public/robots.txt /opt/laravel/public/robots.txt
COPY ./docker/aws/nginx/default.conf /etc/nginx/conf.d/default.conf


ENV TZ Asia/Tokyo
