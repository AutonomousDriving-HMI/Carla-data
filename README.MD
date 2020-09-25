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

#### 3. Carla Running

1. Spawn people & vehicles.

```cmd
cd PythonAPI/examples

python3 spawn_npc.py
```

![alt 2번이미지](/image/img2.png)

#### 4. Carla-ros-bridge Installation

1. add the apt repository
```cmd
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 1AF1527DE64CB8D9
sudo add-apt-repository "deb [arch=amd64] http://dist.carla.org/carla $(lsb_release -sc) main"
```
2. simply install the ROS bridge
```cmd
sudo apt-get update
sudo apt-get install carla-ros-bridge
```
This will install carla-ros-bridge in /opt/carla-ros-bridge.

3. add the PYTHONPATH & setup source file
```cmd
export PYTHONPATH=$PYTHONPATH:<path-to-carla>/PythonAPI/carla/dist/carla-<carla_version_and_arch>.egg
source /opt/carla-ros-bridge/kinetic/setup.bash
```

4. start the RosBridge

- Before we start the RosBridge, we already start the Carla-simulator. 
```cmd
# Option 1: start the ros bridge
roslaunch carla_ros_bridge carla_ros_bridge.launch

# Option 2: start the ros bridge together with an example ego vehicle
roslaunch carla_ros_bridge carla_ros_bridge_with_example_ego_vehicle.launch
```

