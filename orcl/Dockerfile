FROM yekki/oraclelinux:latest

# Maintainer
# ----------
MAINTAINER Gary Niu <gary.niu@oracle.com>

# Environment variables required for this build (do NOT change)
ENV JAVA_PKG=server-jre-8u*-linux-x64.tar.gz
ENV JAVA_HOME /usr/java/default
ENV USER_MEM_ARGS="-Djava.security.egd=file:/dev/./urandom"
ENV PATH=$PATH:/usr/java/default/bin

USER root
RUN echo "root:welcome1" | chpasswd
RUN yum install -y deltarpm
RUN yum install -y oracle-rdbms-server-12cR1-preinstall
RUN yum update -y; yum clean all

RUN echo oracle:oracle | chpasswd

RUN mkdir -p /u01 && chown -R oracle:oinstall /u01 && chmod -R 775 /u01

ADD $JAVA_PKG /usr/java/
RUN mv $(ls -1 -d /usr/java/*) $JAVA_HOME
    
USER oracle
WORKDIR /u01

CMD ["/bin/bash"]