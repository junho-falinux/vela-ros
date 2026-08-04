
flowchart LR
    VELA["vela-ros<br/>ROS 2 Jazzy Build and Packaging<br/>for RISC-V64"]

    subgraph SOURCES["RISC-V-adapted Package Sources"]
        CATKIN["python3-catkin-pkg-modules<br/>ROS Package Metadata Tools"]
        MIMICK["ros-jazzy-mimick-vendor<br/>Mocking Library Vendor Package"]
        BACKWARD["backward_ros<br/>C++ Stack Trace Support"]
        OGRE["ros-jazzy-gz-ogre-next-vendor<br/>Gazebo Rendering Dependency"]
        MPPI["ros-jazzy-nav2-mppi-controller<br/>Nav2 MPPI Controller Plugin"]
    end

    CATKIN -->|"package source"| VELA
    MIMICK -->|"package source"| VELA
    BACKWARD -->|"package source"| VELA
    OGRE -->|"package source"| VELA
    MPPI -->|"package source"| VELA

    VELA -->|"builds and installs DEB packages"| ENV["Vela ROS 2<br/>RISC-V64 Runtime Environment"]

# Prepare
The user have to run qemu-vela ahead and log in. Then, run the script below.

The log in script should output something like this:
-------------------------------------------------------
R9 login: vela
Welcome to Ubuntu 24.04 LTS (GNU/Linux 6.8.0-31-generic riscv64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro
```
vela@R9:~$
```
This confirms that the user is currently running with user privileges for the vela account.

# Check your guest
User have to check the commuication status in this guest env by
```
$sudo apt update
```

Run prepare.sh once initially to set up the system for vela-ros.

```
$./prepare.sh
```

# Build and install ROS2

Run vela-ros for building and installing ros2.

```
$./vela-ros
```

To install specific packages in order, pass package names directly.

```
$./vela-ros ros-jazzy-rclcpp ros-jazzy-ros-base
```

It will take long times(about more than 6 hours). Please be patient.
