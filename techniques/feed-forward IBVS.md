conventional IBVS deals with stationary targets, if the target is moving, we need to introduce the feed-forward IBVS.

the idea is to combine the desired velocity command from the conventional IBVS with the target velocity compensation as a feed-forward term:

$$ v_{d,ff} = v_{d,4DOF}+\hat{v}_{target} $$

where 

$$ \hat{v}_{target} = \begin{bmatrix} \hat{v}_{target,x} & \hat{v}_{target,y} & 0 & 0 \end{bmatrix}^\top $$

is the estimated horizontal velocity of the ship.

