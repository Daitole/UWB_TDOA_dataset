# UWB Time-difference-of-arrival (TDOA) dataset
We provide a UWB time-difference-of-arrival(TDOA) measurement dataset. 

<p align="left">
  <img width="400" height="450" src="./doc/block_diagram.png">
</p>

## Requirements

 - Python 3.x
 - matplotlib
 - numpy, panda
 - scipy, sklearn
 - joblib
 - pytorch (version 1.6.0)
 - tkinter
 
#### Show UWB measurements
run `data_visual.py` and select the measurement data csv 

#### Show UWB measurement biases and neural network regression
run `nn_visual.py` and select the UWB TDOA measurement bias data csv. Set 'WithAn' to 'True' to use the network with anchor orientation and 'False' to use the network without anchor orientation.

## Training Data 
#### UWB TDOA measurement and Vicon groundtruth.
 - /training_csv/meas_data/#Date/#Trajectory
#### UWB TDOA measurement bias and Vicon groundtruth.
 - /training_csv/bias_data/#Data/#Trajectory

## Testing Data 
#### UWB TDOA measurement and Vicon groundtruth.
 - /testing_csv/meas_data/#Date/#Trajectory
#### UWB TDOA measurement bias and Vicon groundtruth.
 - /testing_csv/bias_data/#Data/#Trajectory
 - /testing_csv/bias_data/#Data/#Trajectory/AnchorPos_#Date.npy
 - /testing_csv/bias_data/#Data/#Trajectory/AnchorQuat_#Date.npy
#### anchor position data format
 - row i: position of UWB anchor i in the inertial frame 
 x [m] | y [m] | z [m] 
#### anchor quaternion data format
 - row i: unit quaternion of UWN anchor i in the inertial frame
 q.w | q.x | q.y | q.z  

## Measurement Data Format
#### 1-6 columns
x [m] | y [m] | z [m] | Vicon measurement [m] | UWB TDOA measurement [m] | time [s] 

## Bias Data Format
#### 1-6 columns
Delta x i [m] | Delta y i [m] | Delta z i [m] | Delta x j [m] | Delta y j [m] | Delta z j [m] 
#### 7-10 columns (relative angles in the crazyflie frame)
azimuth angle cf i [deg.] | elevation angle cf i [deg.] | azimuth angle cf j [deg.] | elevation angle cf j [deg.] 

#### 11-14 columns (relative angles in the UWB anchor frame)
azimuth angle an i [deg.] | elevation angle an i [deg.] | azimuth angle an j [deg.] | elevation angle an j [deg.] 

#### 15-16 columns
UWB TDOA bias [m] | time [s]

