FROM ubuntu:18.04
# ONBUILD ADD . /app/src
# ONBUILD RUN /usr/local/bin/python-build --dir /app/src
#MAINTAINER "pavangandham docker" # deprecated use LABEL instead
LABEL "Owner" = "Pavan Gandham"
LABEL "EmailID" = "pavangandham99@gmail.com"
RUN apt update \
    && apt install -y net-tools iputils-ping curl wget jq \
    && apt install -y nginx nano unzip \
    && mkdir /data
COPY script.sh /data/script.sh
ADD terraform /usr/local/bin
ADD https://releases.hashicorp.com/packer/1.7.3/packer_1.7.3_linux_amd64.zip /data/
RUN cd /data/ \
    && unzip packer_1.7.3_linux_amd64.zip \
    && rm -f packer_1.7.3_linux_amd64.zip \
    && mv packer /usr/loacl/bin \
    && packer version
#CMD ["/bin/bash","/data/script.sh"] #  Any CMD command given at the last or successive to preceding ones the these will be ignored.
ENTRYPOINT ["terraform"]
CMD ["version"]     # Here CMD acts as parameter to ENTRYPOINT
ARG NGINX_VERSION=1.17
ARG AWS_CLI=2.0
RUN echo "Available Nginx version :$(NGINX_VERSION)" \
    && echo "Available Aws cli version :$(AWS_CLI)"
VOLUME ["/data/DocVol1"] # creating a volume mount point in the container.
#ENV NGINX_VERSION=1.17
#ENV AWS_CLI=2.0
ENV NGINX=$(NGINX_VERSION)
ENV AWS=$(AWS_CLI)
ENV USERNAME="Pavan Gandham"
ENV PASSWORD="Pavang@1234"
EXPOSE 80 8080 8000
RUN useradd demouser && mkdir /demofolder
WORKDIR /demofolder
USER demouser
HEALTHCHECK --interval=5m --timeout=3s \
  CMD curl -f http://localhost/ || exit 1
STOPSIGNAL SIGQUIT
#CMD ["nginx","-g","daemon off;"]
CMD ["/bin/bash"]           # makes the container to run continuosly without getting deleted after executing the file.

#------------------------------------------------SHELL Command --------------------------------------------------------------------

FROM microsoft/windowsservercore

# Executed as cmd /S /C echo default
RUN echo default

# Executed as cmd /S /C powershell -command Write-Host default
RUN powershell -command Write-Host default

# Executed as powershell -command Write-Host hello
SHELL ["powershell", "-command"]
RUN Write-Host hello

# Executed as cmd /S /C echo hello
SHELL ["cmd", "/S", "/C"]
RUN echo hello
