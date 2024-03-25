FROM openjdk:8
COPY . /src/java
WORKDIR /src/java
RUN ["javac","SampleApp.java"]
ENTRYPOINT ["java","SampleApp"]