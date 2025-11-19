#RBresearch 
### What is Odometry?
Odometry is a method that is used to determine the position of the robot after it has moved based on several parameters. These being:
- Inertial Sensor (Heading)
- Tracking wheel **Parallel** to the direction of travel
- Tracking wheel **Perpendicular** to the direction of travel

### How does it work?
At its core Odometry is all based on one simple equation. Which is as follows: 

dθ: Change in Heading
P: Change in the parallel tracking wheel
s: Tracking wheel's offset from the center
$$
	2sin(dθ/2)*(R/dθ + s)
$$
This equation gives the y translation in **local coordinates**.

Then we can calculate the x axis translation using the perpendicular tracking wheel.
First we need to figure out the expected swing of the tracking wheel since we *are* turning. This can be calculated simply by using the equation for the length of an arc.

t: Tracking wheel offset
$$
t * θ
$$
Then we can subtract that value from the actual tracking wheel change which gives us our x transform. 

Now we have our local coordinates which means all we need to do is rotate the local coordinate system by θ/2.

This gives us the actual transform which we can add to the global position of the robot to get our final position.

Now we can run this equation in a loop in the background using a separate process thread which means no matter what action our robot is preforming it will always be solving for its position.
### What does this allow us to do?

With an exact coordinate tracking system for our robot the possibilities are endless, but most importantly we can create intricate autonomouses without the worry of wheel-slip or drift. 