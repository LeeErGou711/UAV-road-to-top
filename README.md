# UAV-road-to-top
## 8.29
- follow this page to build VRX on my Ubuntu 18.04 and ROS melodic system.
  	- [VRX Classic Tutorials](https://github.com/osrf/vrx/wiki/VRX-Classic-Tutorials)
## 8.30
- follow these blogs to learn to make a UAV simulation in matlab
	- [Guyueju](https://www.guyuehome.com/8981)
	- [CSDN](https://blog.csdn.net/m0_47737058/article/details/115737719)
-  follow the github package using the IBVS method for UAV landing in matlab
	- [QuadcopterVisualServoing](https://github.com/BillyTziv/QuadcopterVisualServoing)

## 8.31
- start to  follow this paper to reproduce the robust IBVS method for UAV landing on a static platform (based on the above IBVS program)
  	- [Robust Image-Based Landing Control of a Quadrotor on an Unpredictable Moving Vehicle Using Circle Features](https://ieeexplore.ieee.org/document/9791477)
  	- (read the source matlab code and try to understand the IBVS algorithm)
- learn YOLO and reproduce YOLO v5 to detect a symbol attached on a platform for UAV landing.
  	- [YOLO v5 official tutorial](https://github.com/ultralytics/yolov5/wiki)
	- [Train a specific model](https://blog.csdn.net/oJiWuXuan/article/details/107558286)
 	- [a useful tool for raw data processing](http://www.jinglingbiaozhu.com/)

## 9.1 (a strong typhoon is approaching SZ :cyclone: :cyclone: :cyclone:)
- collect photo data for the platform for UAV landing, and train the specific YOLO model on Google [colab](https://colab.research.google.com/drive/1H7_7Eba218TUUjTCgBzzS8VF5w8B88k5#scrollTo=X75x6SqI0hmb)
- continue to reproduce the robust IBVS method
## 9.2
- study the wiki of [Prometheus P450 autonomous tracking](https://github.com/amov-lab/prometheus_wiki/blob/main/doc/source/docs/p450/5-%E8%BF%9B%E9%98%B6%E5%8A%9F%E8%83%BD-%E5%AE%A4%E5%86%85%E8%87%AA%E4%B8%BB%E8%B7%9F%E8%B8%AA.rst) and use the above trained model to track the target landing platform

## 9.4 (new semester starts today :kissing_closed_eyes::kissing_closed_eyes::kissing_closed_eyes:)
- upload my trained model [here](https://github.com/LeeErGou711/yolov5/tree/master)
- see the main.ipynb to run it.

## 9.5 
- study VRX: try to control UAV in the simulation environment
- decide to re-build the environment after having a new PC.

## 9.6 
paper reading: 
- [Autonomous ship deck landing of a quadrotor UAV using feed-forward
image-based visual servoing](https://www.sciencedirect.com/science/article/pii/S1270963822005430?ref=pdf_download&fr=RR-2&rr=801fe6e5a8fbcf8b)
	- this paper used IBVS for UAV landing
 	- a feed-forward IBVS was achieved by estimating the velocity of the landing platform (ship)
  	- Kalman filter was introduced for tracking the landing platform
  	- GPS and camera on the UAV werer equipped to guaranteed that the entire landing procedure was fully autonomous.
  	- Square compensation for landing pad oscillation
  	- a specially designed landing markers was proposed to guarantee that the UAV can land from a high attitude
  	- this paper achieved landing on a moving platform with speed 5m/s for the vision-based autonomous landing of a quadrotor UAV
  	- techniques the paper used: conventional IBVS, IBVS with virtual image plane, adaptive-gain IBVS, square compensation, feed-forward IBVS, Kalman filter. (links for a breif introduction to every technique)

## 9.7
summarize techniques used in the paper [Autonomous ship deck landing of a quadrotor UAV using feed-forward
image-based visual servoing](https://www.sciencedirect.com/science/article/pii/S1270963822005430?ref=pdf_download&fr=RR-2&rr=801fe6e5a8fbcf8b), inclued:
- [conventional IBVS](https://github.com/LeeErGou711/UAV-road-to-top/blob/main/techniques/conventional_IBVS.md)
- [feedforward IBVS](https://github.com/LeeErGou711/UAV-road-to-top/blob/main/techniques/feed-forward%20IBVS.md)
- [IBVS with virtual iamge plane](https://github.com/LeeErGou711/UAV-road-to-top/blob/main/techniques/IBVS_for_under-actuated_system.md)
- [adaptive-gain IBVS](https://github.com/LeeErGou711/UAV-road-to-top/blob/main/techniques/adaptive-gain%20IBVS.md)
- [Square compensation for landing pad oscillation]()

## 9.8 
paper reading:
- [Toward visibility guaranteed visual servoing control of quadrotor UAVs](https://ieeexplore.ieee.org/document/8671723)
	- this paper focuses on the visibility problem of ensuring thevisual target stay inside inside the FoV of the camera on the UAV.
   	- control barrier functions are used to derive the visibility constraint and based on the visibility constraint, the visual target will stay within the FoV
   	- a quadratic programming is used to get the best output under the visibility constraint
  	- a non-conservative control barrier functions called Zeroing Barriers Function (ZBF) is used to define the visibility constraint. Here "conservative" means ?
