FROM yekki/oraclelinux:latest

# Maintainer
# ----------
MAINTAINER Gary Niu <gary.niu@oracle.com>

# Environment variables required for this build (do NOT change)

USER root
RUN echo "root:welcome1" | chpasswd
RUN yum -y groupinstall "X Window System"
RUN yum -y install firefox
RUN yum -y install mkfontscale
RUN yum -y install mkfontdir
RUN yum update -y; yum clean all

RUN mkdir /usr/share/fonts/xpfonts
COPY simfang.ttf /usr/share/fonts/xpfonts
RUN mkfontscale
RUN mkfontdir

CMD ["/bin/bash"]