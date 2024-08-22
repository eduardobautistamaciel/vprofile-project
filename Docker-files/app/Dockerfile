
FROM tomcat:8-jre11
LABEL "Project"="Vprofile"
LABEL "Author"="Eduardo"

RUN rm -rf /usr/local/tomcat/webapps/*
COPY target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

# We know we need to run "catalina.sh" ref. https://hub.docker.com/_/tomcat
CMD ["catalina.sh", "run"]
WORKDIR /usr/local/tomcat
VOLUME /usr/local/tomcat/webapps
