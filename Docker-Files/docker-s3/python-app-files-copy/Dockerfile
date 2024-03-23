FROM python:3.8

LABEL description="In this we are trying to copy the python application files in s3 bucket to docker"
MAINTAINER <Pavan_Gandham>

ARG AWS_ACCESS_KEY_ID
ARG AWS_SECRET_ACCESS_KEY

COPY ./app
WORKDIR /app

# Installing aws-cli
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN ./aws/install

# Copying the files from s3 to /app directory in docker
RUN aws s3 cp --recursive s3://<YOUR-PYTHON-APP-BUCKET-NAME> /app

RUN pip install -r requirements.txt
CMD ["python", "app.py"]