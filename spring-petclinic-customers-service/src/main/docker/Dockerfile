FROM java:8
VOLUME /tmp
ADD https://raw.githubusercontent.com/vishnubob/wait-for-it/master/wait-for-it.sh wait-for-it.sh
RUN bash -c 'chmod +x wait-for-it.sh'
ARG ARTIFACT_NAME
ADD ${ARTIFACT_NAME}.jar /app.jar
ENV SPRING_PROFILES_ACTIVE docker
RUN bash -c 'touch /app.jar'
EXPOSE 8081
EXPOSE 9092
EXPOSE 5005
ENTRYPOINT ["java","-DpromPort=9092","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
