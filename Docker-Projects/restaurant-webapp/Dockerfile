FROM httpd:2.4-alpine

LABEL Maintainer="Pavan Gandham Corp"
LABEL Email="pavangandham99@gmail.com"

# Updating alpine packages
RUN apk update

#Copying file into Httpd server
COPY ./*.html /var/www/html/
COPY ./.css /var/www/html/
COPY ./img/*.jpg /var/www/html/
COPY ./img/*.gif /var/www/html/