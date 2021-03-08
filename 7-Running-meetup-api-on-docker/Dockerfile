FROM centos

# -y says yes to y/n questions during java instalation
RUN yum install -y java 

# /tmp is used to store temporal springboot embebed tomcat files
VOLUME /tmp
#Add the war artifact from current folder 
#into the image and renamed the jar to meetup.jar
ADD meetup-0.0.1-SNAPSHOT.jar meetup.jar
#with touch we update artifact date to avoid image layers cache
RUN sh -c 'touch /meetup.jar'
#This command helps tomcat and our .jar to start faster
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom","-jar","/meetup.jar"]

EXPOSE 8080