This project is cloned from https://github.com/ethz-asl/kalibr

Follow the next steps to calibrate the extrinsic parameters of monocular and imu:

1. $rosbag record -a 

   record the bag including your imu and image topic offline

2. $rosrun kalibr kalibr_calibrate_cameras --target checkerboard.yaml --bag /home/peiliang/2016-11-24-22-47-29.bag --models pinhole-radtan --topics /djiros/image

    make sure checkboard.yaml file is in the running directory and edit it according to your target board

3.$rosrun kalibr kalibr_calibrate_imu_camera --bag /home/peiliang/2016-11-24-22-47-29.bag --cam camchain-homepeiliang2016-11-24-22-47-29.yaml --imu imu.yaml --target checkerboard.yaml

    make sure the camchain-homepeiliang2016-11-24-22-47-29.yaml is generated from previous step and edit imu.yaml according to your sensor

4.wait 1 hour for the result
