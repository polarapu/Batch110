FROM redhat/ubi9
MAINTAINER "Prasad"
RUN touch /opt/file1
RUN mkdir /opt/dir1
RUN yum install git -y
WORKDIR /opt
RUN git clone https://github.com/polarapu/batch111.git
RUN yum install wget -y
RUN wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.44/bin/apache-tomcat-10.1.44.tar.gz
RUN tar -xvf apache-tomcat-10.1.44.tar.gz
COPY tomcat-users.xml /opt/apache-tomcat-10.1.44/conf/
EXPOSE 8989
#ENV export JAVA_HOME=/path
#CMD git --version
ENTRYPOINT git --version
