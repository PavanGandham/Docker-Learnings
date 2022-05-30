FROM nginx:1.21.6-alpine

LABEL Maintainer="Pavan Gandham Corp"
LABEL Email="pavangandham99@gmail.com"

#Updating alpine packages
RUN apk update

#Configurations
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./*.html /usr/share/nginx/html/
COPY ./*.css /usr/share/nginx/html/
COPY ./*.js /usr/share/nginx/html/
COPY ./output/*.mp4 /usr/share/nginx/html/
COPY ./output/*.png /usr/share/nginx/html/

