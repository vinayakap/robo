1. **Install WSL2** following instructions [here](https://learn.microsoft.com/en-us/windows/wsl/install).
2. Download XLaunch using [this link](https://excellmedia.dl.sourceforge.net/project/vcxsrv/vcxsrv/1.20.14.0/vcxsrv-64.1.20.14.0.installer.exe).
3. Install Ubuntu 22.04 LTS from Microsoft Store and set up a username and password.

4. Set the following environment variables:
    ```bash
   export GAZEBO_IP=127.0.0.1
   export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
   export LIBGL_ALWAYS_INDIRECT=0
    ```
5. Go to [ROS Installation Documentation](http://docs.ros.org/en/iron/Installation/Ubuntu-Install-Debians.html) for detailed instructions or follow the steps below directly.

6. Enable required repositories:
   ```bash
   sudo apt install software-properties-common
   sudo add-apt-repository universe
   sudo apt update && sudo apt install curl -y
   sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
   echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
    ```

7. Install development tools:
   ```
   sudo apt update && sudo apt install ros-dev-tools
   ```

8. Install ROS2:
  `sudo apt update` <br/>
  `sudo apt upgrade` <br/>
  `sudo apt install ros-iron-desktop` <br/>
  `sudo apt install ros-iron-ros-base` <br/>

9. Set up the environment:
   ```bash
   source /opt/ros/iron/setup.bash
   ```

10. Install Gazebo (from [official Gazebo tutorial](https://classic.gazebosim.org/tutorials?tut=install_ubuntu)):
    ```bash
    curl -sSL http://get.gazebosim.org | sh
    ```

11. Run Gazebo:
    ```bash
    gazebo
    ```

12. [Additional Steps or Notes]
