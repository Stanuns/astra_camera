参考：README.md; https://blog.csdn.net/joyopirate/article/details/130219247
适配ros2 humble

Install dependencies

```bashrc
sudo apt install libgflags-dev nlohmann-json3-dev \
ros-humble-image-transport ros-humble-image-publisher
```

Install glog

```bashrc
wget -c https://github.com/google/glog/archive/refs/tags/v0.6.0.tar.gz  -O glog-0.6.0.tar.gz
tar -xzvf glog-0.6.0.tar.gz
cd glog-0.6.0
mkdir build && cd build
cmake .. && make -j4
sudo make install
sudo ldconfig  # Refreshing the link library
```

Install magic_enum

```bashrc
wget -c https://github.com/Neargye/magic_enum/archive/refs/tags/v0.8.0.tar.gz -O  magic_enum-0.8.0.tar.gz

tar -xzvf magic_enum-0.8.0.tar.gz
cd magic_enum-0.8.0
mkdir build && cd build
cmake .. && make -j4
sudo make install
sudo ldconfig # Refreshing the link library
```

Install libuvc

```bashrc
git clone https://github.com/libuvc/libuvc.git
cd libuvc
mkdir build && cd build
cmake .. && make -j4
sudo make install
sudo ldconfig # Refreshing the link library
```

### Getting Started

Install libusb rules

```bashrc
cd ~/ros2_ws/src/ros2_astra_camera/astra_camera/scripts
sudo bash install.sh
sudo udevadm control --reload-rules && sudo udevadm trigger
```

build
进入~/orbbec_ws目录中

```
colcon build --event-handlers  console_direct+  --cmake-args  -DCMAKE_BUILD_TYPE=Release
```

```
ros2 launch astra_camera astra_mini.launch.py
```

camera_link camera_depth_optical_frame: ob_camera_node.cpp
