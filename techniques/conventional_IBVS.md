## a brief introduction to conventional IBVS (image based visual servoing)

in a word, IBVS is to extract characteristics from images catpured by cameras and output expected position and velocity to control the motion of the robot.

the objective of IBVS is to reduce the pixel error between the desired and measured feature positions in the image plane. $$e = s_d-s$$ where e is the error, $s_d$ is the desired feature position and $s$ is the measured feature position.

we have the following relationship between the camera and the feature velocity: $$\dot{s} = L_sv_c$$ where $L_s$ denotes the image Jacobian matrix (which is the relationship between the velocity of the feature in the iamge plane and the camera velocity), and $v_c$ denotes the camera velocity comprising three linear motinos and three angular motions
i.e., $v_c = [v_{c,x}, v_{c,y}, v_{c,z},\omega_{c,x},\omega_{c,y},\omega_{c,z}]\in \mathcal{R}^6$

to define $s$: an arbitrary point $P= [x ~y ~z]^\top$ in the camera frame ($O_{XYZ}$) is projected to the image plane as $s = [x',y']^\top$ $$x' = fx/z$$ $$y' = fy/z$$ where $f$ denotes the camera focal length. 

assume that the desired feature position $s_d$ is static, i.e., $\dot{e} = \dot{s}$, we know that $\dot{s} = L_sv_c$ and thus we have $$v_c = \dot{s}L_s^{-1}$$. note that $L_s\in \mathcal{R}^{2\times6}$, which is not invertible, so we replace $L_s$ by its psude inverse: $L_s^+ = (L_s^{\top}L_s)^{-1}L_s^{\top}$, so we have $$c_c = L_s^+\dot{e}$$

to ensure that the feature error decreases exponentially. i.e., $\dot{e} = -\lambda e$, we have $$v_c = -\lambda L_s^+e$$ we designed a velocity controller 

remarks:
- we get $e = s_d-s$ by setting $s_d$ previously and update $s$ in every iteration.
- $L_s$ can be obtained as

$$L_s = 
\begin{bmatrix}
-\frac{f}{z} & 0 & \frac{x^\prime}{z} & \frac{x^\prime y^\prime}{f} & \frac{-(f^2+x^{\prime 2})}{f} & y^\prime \\
0 & -\frac{f}{z} & \frac{y^\prime}{z} & \frac{f^2+y^{\prime 2}}{f} & \frac{-x^\prime y^\prime}{f} & -x^\prime
\end{bmatrix}
$$
