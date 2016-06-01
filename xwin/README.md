# Build image
    
    docker build --build-arg http_proxy=$http_proxy -t yekki/oraclelinux-xwin .

# How to run xwindows in OSX

* open XQuartz in osx
* open terminal and run socat in osx

    $socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"

* run docker container with ovirtualbox ip in osx
    
    docker run -it -e DISPLAY=10.182.245.22:0 --name xwin yekki/oraclelinux-xwin:latest /bin/bash


PS: The DISPLAY IP is your osx host IP(VNIC), the IP is different based on your virtual machine solution, in this example, for Parallels Desktop, the IP should be 10.211.55.2:0, for Virtual Box, the IP should be 192.168.99.1:0. And if you use Docker for Mac native(what I test above), the IP should be the IP of en0.