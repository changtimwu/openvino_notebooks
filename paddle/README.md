## Enhancements to execute examples written in paddlepaddle framework

### Introduction
This container is combination the following
* Ubuntu 20
* Openvino 2022
* Intel NNCF framework
* paddlepaddle framework

### Build
Build the container
```
docker build -t openvino_juypter -f Dockerfile .
```

### Usage 

* activate the container with script like this
``` sh
port_opts="-p 8888:8888"
asroot_opts="-u root:root"
repohostdir=`realpath ${PWD}/..`
vol_opts="-v ${repohostdir}:/root/notebooks"
cam_opts=" --device=/dev/video0"
docker run -it $asroot_opts $port_opts $vol_opts $cam_opts --rm  openvino_juypter 
```
* open http://<container host>:8888/ enter jupyter lab environment
* You are supposed to check `notebooks/405-paddle-ocr-webcam` first


