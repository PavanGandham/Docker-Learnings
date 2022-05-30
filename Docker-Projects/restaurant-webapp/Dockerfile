FROM httpd:2.4-alpine

LABEL Maintainer="Pavan Gandham Corp"
LABEL Email="pavangandham99@gmail.com"

# Updating alpine packages
RUN apk update

#Copying file into Httpd server
COPY ./*.html /usr/local/apache2/htdocs/
COPY ./*.css /usr/local/apache2/htdocs/
COPY ./img/*.jpg /usr/local/apache2/icons/
COPY ./img/*.gif /usr/local/apache2/icons/