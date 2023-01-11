# UCL_AIR_ROS

## Set Up Catkin workspace

We use `catkin build` instead of `catkin_make`. Please install the following:

```
sudo apt-get install python3-wstool python3-rosinstall-generator python3-catkin-lint python3-pip python3-catkin-tools
pip3 install osrf-pycommon
```

Then, initialize the catkin workspace:
```
mkdir -p ~/catkin_ws/src
cd ~/UCLAIR_ws
UCLAIR_was init
```

## Install `mavros` and `mavlink`

Install `mavros` and `mavlink` from source:
```
cd ~/UCLAIR_ws
wstool init ~/UCLAIR_ws/src

rosinstall_generator --upstream mavros | tee /tmp/mavros.rosinstall
rosinstall_generator mavlink | tee -a /tmp/mavros.rosinstall
wstool merge -t src /tmp/mavros.rosinstall
wstool update -t src
rosdep install --from-paths src --ignore-src --rosdistro `echo $ROS_DISTRO` -y

catkin build
```
Add a line to end of `~/.bashrc` by running the following command:
```
echo "source ~/UCLAIR_ws/devel/setup.bash" >> ~/.bashrc
```

update global variables
```
source ~/.bashrc
```





## 5. Build instructions
Inside `UCLAIR_ws`, run `catkin build`:

```
cd ~/UCLAIR_ws
catkin build
```
update global variables
```
source ~/.bashrc
```
