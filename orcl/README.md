# Build image

    docker build --build-arg http_proxy=$http_proxy -t yekki/oracle-base:latest .

add --env http_proxy=http://10.188.60.183:80(change to yours) if your host behind proxy and you don't wanna leave proxy setting in your container.

