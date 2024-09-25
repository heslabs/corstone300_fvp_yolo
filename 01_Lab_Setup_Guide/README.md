# Lab Setup Guide

### Accessing the Labs Files
Download the lab files from labs sftp site as below. The lab repository includes the required Github project, scripts and Makefile. Extract tar file from Linux terminal and navigate to the cs300fvp/runtime, which is the working directory.

The lab repository is based on the following Github projects from Arm and ecosystem partner 
* Github Running YOLOv8 on Himax WE2 [[Github]](https://github.com/anitawuitri/YOLOv8_on_WE2.git)  
* Deploy examples on FVP simulation environment [Github](https://github.com/HimaxWiseEyePlus/ML_FVP_EVALUATION?tab=readme-ov-file#how-to-use-himax-config-file-to-generate-vela-model) 
* Arm ML Embedded Evaluation Kit [[GitHub]](https://review.mlplatform.org/plugins/gitiles/ml/ethos-u/ml-embedded-evaluation-kit/)


---
### Clone the Github repositories
Clone the Github repositories if you want to build the environment without Docker (optional)
```
$ git clone -b ci_env https://github.com/anitawuitri/YOLOv8_on_WE2.git 
$ git clone https://github.com/HimaxWiseEyePlus/ML_FVP_EVALUATION.git
$ git clone "https://review.mlplatform.org/ml/ethos-u/ml-embedded-evaluation-kit" 
```

---
### Download Docker Image

To run ML applications on the Cortex-M and Ethos-U NPU, the following development tools are required to be installed. The recommended flow is to build Docker environment using reference Dockerfile in Arm ML Embedded Evaluation Kit (/ml-embedded-evaluation-kit/Dockerfile)

The pre-built Docker image includes the following required version of development tools 
* Ubuntu 20.04 x86-64
* GNU Arm Embedded Toolchain [Link]
* gcc-arm-none-eabi-10.3-2021.10-x86_64-linux.tar.bz2 
* ml-embedded-evaluation-kit
  * https://review.mlplatform.org/plugins/gitiles/ml/ethos-u/ml-embedded-evaluation-kit/+archive/refs/tags/22.02.tar.gz 
* Arm Corstone-300 FVP: 
  * FVP_Corstone_SSE-300_Ethos-U55_11.14_24.tgz [Download]
* Vela compiler for Ethos-U NPU
```
$ sudo pip install ethos-u-vela
Successfully installed: ethos-u-vela-3.6.0, flatbuffers-2.0.7, numpy-2.0.1
```



---
### Install Docker on Ubuntu Linux
```
$ sudo snap install docker 
```

Run docker as non-root user then you need to add it to the docker group
```
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
$ sudo chmod 666 /var/run/docker.sock
$ sudo systemctl restart docker
```
Check if docker can be run without root
```
$ docker run hello-world
```

---
### Install Docker on Ubuntu Linux
```
$ sudo snap install docker 
```
