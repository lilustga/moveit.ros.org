---
layout: install
slug: source_install_moveit2_windows
title: MoveIt 2 Source Build - Linux
---
{% include install-feedback.html %}

# MoveIt 2 Source Build - Windows

Installing MoveIt 2 from source is the first step in contributing new features, optimizations, and bug fixes back to the open source project. Thanks for getting involved!

<img class="docker-img" src="/assets/install_page/docker-illustration.png"/>

## Prerequisites

ROS for Windows requires 64-bit Windows 10 Desktop or Windows 10 IoT Enterprise.

### Install ROS 2 on Windows

Follow all the <a href="http://wiki.ros.org/Installation/Windows" target="_blank">Install ROS on Windows</a> instructions to install ROS2. Make sure to follow step 5.2 instead of 5.1.

## Moveit 2 Source Installation on Windows

MoveIt Source Installation on Windows

Open an elevated ROS Command Window as described in the installation instructions (x64 Native Tools Command Prompt).

### Create Workspace and Source

Optionally create a new workspace, you can name it whatever:

    :: activate the ROS environment
    c:\opt\ros\melodic\x64\setup.bat
    
    :: create a empty workspace
    mkdir c:\moveit_ws\src
    cd c:\moveit_ws\src

## Download Source Code

Download the repository and install any dependencies:

    git clone https://github.com/ms-iot/moveit2.git -b windows-port
    vcs import < moveit2/moveit2.repos

## Build MoveIt

Configure and build the workspace:

    cd c:\moveit_ws\
    colcon build --event-handlers desktop_notification- status- --cmake-args -DCMAKE_BUILD_TYPE=Release

### Source the Colcon Workspace

Setup your environment:

    install\setup.bat

### Quick Start

We've prepared a simple demo setup that you can use for quickly spinning up a simulated robot environment with MoveItCpp.

<a href="https://github.com/ros-planning/moveit2/tree/main/moveit_demo_nodes/run_moveit_cpp" target="_blank">
  <span class="link-with-background">
    MoveItCpp Demo Package
  </span>
</a>
