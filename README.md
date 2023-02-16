# ros_vision_track

## Directory Structure
```
├── ros_vision_track
│   ├── config
│   │   └── rviz
│   ├── ros_vision_track
│   │   └── camera_processing
│   │       ├── trackers
│   │       ├── weights
│   │       └── yolov5
│   ├── launch
│   ├── resource
│   └── test
```
<!---
tree -d -L 3 -I __pycache__
--->

> **Note:** This is setup like a ROS2 package, but you do not need to build it to run the scripts. However to use launch files the package needs to be built.
# Setup

To get started
```
git clone --recurse-submodules https://github.com/adrian-soch/ros_vision_track.git
```


### Install Python requirements
```
# Pytorch GPU Version go here: https://pytorch.org/get-started/locally/

# (Optional) PyTorch CPU Version
pip install torch torchvision

pip install numpy

# OpenCV CPU Version
pip install opencv-python
pip install opencv-contrib-python
```

### Yolov5 requirements
```
numpy>=1.18.5
opencv-python>=4.1.1
Pillow>=7.1.2
psutil  # system resources
PyYAML>=5.3.1
requests>=2.23.0
scipy>=1.4.1
```

# Running the Code

## Image detection and tracking:
```
# Play the rosbag
ros2 bag play <Path to rosbag>/<bag name>.db3

# Start the python code
cd <Path to ros_vision_track>/ros_vision_track
python3 camera_processing_yolovX_node.py
```

## Modifying parameters
To modify the parameters go to `ros_vision_track/camera_processing/vision_track.py`.

## References

1. https://github.com/ultralytics/yolov5
2. https://github.com/WongKinYiu/yolov7
3. https://github.com/mikel-brostrom/Yolov5_StrongSORT_OSNet
