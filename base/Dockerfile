FROM fabric8/java-centos-openjdk7-jdk:latest

USER root

# install tools
RUN yum update -y && yum install -y unzip wget dos2unix

WORKDIR /root

# install apache-ant
RUN wget --no-check-certificate -O /root/apache-ant-1.7.1-bin.zip http://archive.apache.org/dist/ant/binaries/apache-ant-1.7.1-bin.zip
RUN unzip /root/apache-ant-1.7.1-bin.zip

RUN wget --no-check-certificate https://nchc.dl.sourceforge.net/project/ant-contrib/ant-contrib/ant-contrib-1.0b2/ant-contrib-1.0b2-bin.tar.gz
RUN tar xzf ant-contrib-1.0b2-bin.tar.gz
RUN cp ant-contrib/lib/ant-contrib.jar /root/apache-ant-1.7.1/lib/

ENV ANT_HOME /root/apache-ant-1.7.1
ENV PATH $JAVA_HOME/bin:$GRAILS_HOME/bin:$ANT_HOME/bin:$PATH

RUN chmod 701 /root

RUN rm /root/apache-ant-1.7.1-bin.zip
RUN rm /root/ant-contrib-1.0b2-bin.tar.gz
RUN rm -rf /root/ant-contrib
