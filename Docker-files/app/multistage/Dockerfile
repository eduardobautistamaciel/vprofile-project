FROM openjdk:8 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone -b ci-jenkins https://github.com/eduardobautistamaciel/vprofile-project.git
RUN cd vprofile-project && mvn install

FROM tomcat:8-jre11

RUN rm -rf /usr/local/tomcat/webapps/*

COPY --from=BUILD_IMAGE vprofile-repo/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
# We know we need to run "catalina.sh" ref. https://hub.docker.com/_/tomcat
CMD ["catalina.sh", "run"]