
---

# ROS 2 (Jazzy) Installation Guide

This guide provides step-by-step instructions for installing ROS 2 Jazzy (Ubuntu Noble 24.04), whether you're using WSL or a live environment.

## Table of Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Uninstallation](#uninstallation)
- [Additional Resources](#additional-resources)

## Requirements

- **Operating System**: Ubuntu 24.04 (WSL or live)

## Installation

To install ROS 2 Jazzy, run the following commands in your terminal:

```bash
# Check locale and ensure UTF-8 support
locale  # Check for UTF-8
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
locale  # Verify settings

# Enable the Ubuntu Universe repository
sudo apt install software-properties-common
sudo add-apt-repository universe

# Add the ROS 2 GPG key
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

# Add ROS 2 repository to sources list
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

# Install ROS 2 development tools and Jazzy Desktop
sudo apt update && sudo apt install ros-dev-tools
sudo apt update
sudo apt upgrade
sudo apt install ros-jazzy-desktop

# If you only want the base installation, uncomment the line below:
# sudo apt install ros-jazzy-ros-base

# Setup ROS 2 environment (add this to your bash configuration)
echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

## Uninstallation

To completely uninstall ROS 2 Jazzy, run the following commands:

```bash
sudo apt remove ~nros-jazzy-* && sudo apt autoremove
sudo rm /etc/apt/sources.list.d/ros2.list
sudo apt update
sudo apt autoremove
# Consider upgrading for packages previously shadowed.
sudo apt upgrade
```

## Additional Resources

For more detailed information, refer to the official ROS 2 documentation: [ROS 2 Documentation: Jazzy](https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html#)

---

