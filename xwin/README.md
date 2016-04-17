# Build image
    
    docker build -t yekki/oraclelinux-xwin:latest .

# How to run xwindows in OSX

* open XQuartz in osx
* open terminal and run socat in osx

    $socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"

* run docker container with ovirtualbox ip in osx
    
    docker run -it -e DISPLAY=10.211.55.2:0 --name xwin yekki/oraclelinux-xwin:latest /bin/bash


PS: The DISPLAY IP is your osx host IP(VNIC), the IP is different based on your virtual machine solution, in this example, I use Parallels Desktop, if you use Virtual Box, the IP may be 192.168.99.1:0.