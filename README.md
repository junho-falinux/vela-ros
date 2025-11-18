# Prepare
The user must first run qemu-vela and log in. Then, run the script below.

The script should output something like this:
-------------------------------------------------------
R9 login: vela
Welcome to Ubuntu 24.04 LTS (GNU/Linux 6.8.0-31-generic riscv64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro
```
vela@R9:~$
```
-------------------------------------------------------
This confirms that the user is currently running with user privileges for the vela account.

Run prepare.sh once initially to set up the system for vela-ros.
User have to ckeck the commuication status by
$sudo apt get update
```
$./prepare.sh
```

# Build and install ROS2

Run vela-ros for building and installing ros2.

```
$./vela-ros
```
