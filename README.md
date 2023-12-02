## Install WSL2
Follow instructions in this [official link](https://learn.microsoft.com/en-us/windows/wsl/install).
## Install XLaunch
Download XLaunch using [this link](https://excellmedia.dl.sourceforge.net/project/vcxsrv/vcxsrv/1.20.14.0/vcxsrv-64.1.20.14.0.installer.exe).

## Install Ubuntu 22.04 LTS
Available on  Microsoft Store 
Set up a username and password.

### Set the following environment variables:
    ```bash
    export GAZEBO_IP=127.0.0.1
    ```
    ```bash
    export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
    ```
    ```bash
    export LIBGL_ALWAYS_INDIRECT=0
    ```
### ROS Installation Documentation
Go to [ROS Installation Documentation](http://docs.ros.org/en/iron/Installation/Ubuntu-Install-Debians.html) for detailed instructions 
or follow the steps below directly.

### Enable required repositories
```bash
sudo apt install software-properties-common
```
```bash
sudo add-apt-repository universe
```
```bash
sudo apt update && sudo apt install curl -y
```
```bash
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

### Install development tools

```
sudo apt update && sudo apt install ros-dev-tools
```

### Install ROS2

```bash 
sudo apt update
``` 
```bash
sudo apt upgrade
```
```bash
sudo apt install ros-iron-desktop
```
```bash 
sudo apt install ros-iron-ros-base
```

### Set up the environment:

```bash
source /opt/ros/iron/setup.bash
```

### Install Gazebo
[official Gazebo tutorial](https://classic.gazebosim.org/tutorials?tut=install_ubuntu)

or

```bash
curl -sSL http://get.gazebosim.org | sh
```

### Run Gazebo
    ```bash
    gazebo
    ```

### Additional Steps or Notes
