a bried introduction to IBVS for under-actuated system

quadrotor UAV is a kind of under-actuated system: roll and pitch rates are coupled with the linear velocities in he y and x directions, respectively. In other words, the UAV cannot make roll and pitch rate motions independent of y- and x-axis velocities.

this under-actuated nature may lead to unwanted problems, so a virtual coordinate frame is adopted. 

the virtual coordinate is defined such that 
- the center of the origin coincides with the camera coordinate frame and its z-axis is parallel to the z-axis of the inertial frame.
- the image plane is rotated from the camera frame to the virtual coordinate frame
- the virtual image plane is always parallel to the ground (then the roll and pitch rates are always zero, an under-actuated system can be decoupled.)

we conduct the virtual image plane transformation using the roll and pitch angles of the UAV: consider a 3-D position in the camera frame $P = [x ~y ~z]^{\top}$, whose virtual coordinate is $P^r = [x_r ~y_r ~z_r]^\top$, and its 2-D position in the image plane and virtual image plane are $s$ and $s^r$

the relationship between $P$ and $P^r$ can be expressed as $$P^r = R(1,\phi)R(2,\phi)P$$ where 

$$
R(1, \phi)=
\begin{bmatrix}
1 & 0 & 0 \\
0 & \cos \phi & -\sin \phi \\
0 & \sin \phi & \cos \phi
\end{bmatrix}
$$

$$
R(2, \theta)=
\begin{bmatrix}
\cos \theta & 0 & \sin \theta \\
0 & 1 & 0 \\
-\sin \theta & 0 & \cos \theta
\end{bmatrix}
$$

and, $\phi$ and $\theta$ are roll and pitch angle of the UAV, respectively. the $i$-th marker position in the virtual image plane can be computed as:

$$
\boldsymbol{s}^r=\frac{f}{z^r}\begin{bmatrix}
x^r \\
y^r
\end{bmatrix}=f\begin{bmatrix}
\frac{x^{\prime} \cos \theta+f \sin \theta}{-x^{\prime} \cos \phi \sin \theta+y^{\prime} \sin \phi+f \cos \phi \cos \theta} \\
\frac{x^{\prime} \sin \phi \sin \theta+y^{\prime} \sin \phi+f \cos \phi \cos \theta}{-x^{\prime} \cos \phi \sin \theta+y^{\prime} \sin \phi+f \cos \phi \cos \theta}
\end{bmatrix}.
$$
