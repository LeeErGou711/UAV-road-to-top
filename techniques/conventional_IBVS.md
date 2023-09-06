## a brief introduction to conventional IBVS (image based visual servoing)

in a word, IBVS is to extract characteristics from images catpured by cameras and output expected position and velocity to control the motion of the robot.

the objective of IBVS is to reduce the pixel error between the desired and measured feature positions in the image plane. $$e = s_d-s$$ where e is the error, $s_d$ is the desired feature position and $s$ is the measured feature position.

we have the following relationship between the camera and the feature velocity: $$\dot{s} = L_sv_c$$ where $L_s$ denotes the [image Jacobian matrix]() (which is the relationship between the velocity of the feature in the iamge plane and the camera velocity), and $v_c$ denotes the camera velocity comprising three linear motinos and three angular motions
i.e., $v_c = [v_{c,x}, v_{c,y}, v_{c,z},\omega_{c,x},\omega_{c,y},\omega_{c,z}]\in \mathcal{R}^6$

to define $s$: an arbitrary point $P= [x y z]^top$ in the camera frame ($O_{XYZ}$) is projected to the image plane as $s = [x',y']^\top$ $$x' = fx/z$$ $$y' = fy/z$$ where $f$ denotes the camera focal length. 
