# OVERVIEW

1. HDMAP DATA
2. ROSBAG DATA
    1. Development Environment
    2. Carla installation

## 1. HDMAP DATA
- Using OpenDrive Map (folder name : OpenDrive)

## 2. ROSBAG DATA
- Doing Carla Simulator
- Link : https://carla.readthedocs.io/en/latest/

#### 1. Development Environment
- os : Ubuntu 16.04
- package : pygame, numpy
- version : pip3, python3.7

#### 2. Carla Installation

1. Install pygame

```cmd
pip install --user pygame numpy
```

2. deb package installation of CARLA 0.9.9 (only Linux)

```cmd 
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 92635A407F7A020C

sudo add-apt-repository "deb [arch=amd64 trusted=yes] http://dist.carla.org/carla-0.9.9/ all main"

sudo apt-get update

sudo apt-get install carla-simulator

cd /opt/carla-simulator/bin

./CarlaUE4.sh
```

![alt 1번이미지](/image/img1.png)
