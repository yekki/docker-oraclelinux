FROM oraclelinux

MAINTAINER Gary Niu <gary.niu@oracle.com>

#ENV http_proxy=http://10.188.60.183:80

RUN yum -y update \
	&& yum -y groupinstall "X Window System" \
	&& yum -y install firefox \
	&& yum -y install mkfontscale \
	&& yum -y install mkfontdir \
	&& yum clean all

RUN mkdir /usr/share/fonts/xpfonts

COPY simfang.ttf /usr/share/fonts/xpfonts

RUN mkfontscale && mkfontdir

CMD ["/bin/bash"]