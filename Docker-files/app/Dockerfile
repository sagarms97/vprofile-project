#Openjdk image
FROM OpenJDK:11 AS IMAGE_BUILD
LABEL project="vprofile"
RUN apt update && apt install maven -y
RUN git clone -b docker https://github.com/sagarms97/vprofile-project.git
RUN cd vprofile-project && mvn install

#tomcat image
FROM tomcat:9-jre11
LABEL project="vprofile"
RUN rm -rf /usr/local/tomcat/webapps/*
copy --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh", "RUN"]

