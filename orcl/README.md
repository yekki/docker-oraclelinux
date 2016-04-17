
# Download latest server jre

    curl -v -j -k -L -H "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u77-b03/server-jre-8u77-linux-x64.tar.gz > server-jre-8u77-linux-x64.tar.gz

# Build image

    docker build -t yekki/oracle-base:latest .
