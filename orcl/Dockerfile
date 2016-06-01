FROM oracle/jdk:8

MAINTAINER Gary Niu <gary.niu@oracle.com>

#ENV http_proxy=http://10.188.60.183:80

RUN yum -y update \
	&& yum -y install unzip \
	&& yum -y install oracle-rdbms-server-12cR1-preinstall \
	&& yum clean all

RUN userdel oracle \
	&& rm -rf /home/oracle \
	&& rm /var/spool/mail/oracle \
	&& useradd -m -u 54321 -g oinstall -G dba oracle \
	&& echo "oracle:oracle" | chpasswd \
	&& mkdir -p /u01 && chown -R oracle:oinstall /u01 && chmod -R 775 /u01

CMD ["/bin/bash"]