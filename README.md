
# Task 1: Install Ros into Ubuntu

This file will represent the steps to install Robot Operating System (ROS) into Ubuntu.

## Versions
ROS noetic does not support Ubuntu 22.04. So, I use Ubuntu 20.04.1
- Ubuntu 20.04.1 
- ROS noetic


 
## Installation steps

#### 1. Setup Ubuntu repositories
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

#### 2. Setup the keys
If you haven't already installed curl
```bash
sudo apt install curl
```
```bash
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

#### 3. Installation
Make sure the package is up to date

```bash
sudo apt update
```
Then pick which ROS you would like to install

- Desktop-Full Install: (Recommended) : Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages 
```bash
sudo apt install ros-noetic-desktop-full
```
- Desktop Install: Everything in ROS-Base plus tools like rqt and rviz 
```bash
sudo apt install ros-noetic-desktop
```
- ROS-Base: (Bare Bones) ROS packaging, build, and communication libraries. No GUI tools. 
```bash
sudo apt install ros-noetic-ros-base
```
If we want to install a specific package we can use this command:

```bash
sudo apt install ros-noetic-PACKAGE NAME
```
Also, to find the other available packages, use:

```bash
apt search ros-noetic
```
##### 4. Setup the enviroment
we should source this scipt in every bash terminal we use ROS in. but in my opinion, practically it's not convenient.
```bash
source /opt/ros/noetic/setup.bash
```
It will be more convenient to automatically source this script every time er launched a new shell. There are couple of commands that will do that for us.

- Bash 
```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
- Zsh
```bash
echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
```

#### 5. Dependencies for building packages
To install the tool and other dependencies for building ROS packages, run: 
```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

##### 5.1. Initialize rosdep
If you have not yet installed rosdep, use: 
```bash
sudo apt install python3-rosdep
```
Initialize rosdep and update it
```bash
sudo rosdep init
rosdep update
```
