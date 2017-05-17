Lab 2 - Potential Fields

Main Objectives:
 - Create attractive fields
 - Create detractive fields
 - Add another field
 - Use fields to navigate robot


 Sub-objectives and functions:
  - Field calculation
	- Get attractive field value at a given point
	- Get detractive field values at a given point
	- Obtain a sum result of all fields
  - Field visualization
  	- Create a grid
  	- Calculate field values for each point
  	- Draw a vector for each field value
  - Robot movement
  	- Get global desired velocity from field
  	- Convert global velocity to body velocity
  	- Command wheel speeds to obtain desired velocity
  	- Feedback control for velocity?




  	Robot Movement:
  	 - Possible options
  	 	- (1) Rotate in place to get desired angle, then move forward
  	 	- (2) Check forward and use a circle to get into the right angle for the nearest vector

  	(2) Check forward and use a circle to get into the right angle for the nearest vector:
  	 - Set length parameter, L, to propogate the current forward vector (v1), starting at p1
  	 - Grab the vector at the point L distance in front of the robot (v2), ending at p2
  	 - Find a circle that will go from p1 to p2 with v1 and v2 tangent to the circle at their respective places

  	alpha = angle between v1 and v2
  	L = propogation distance
  	R = L*tan((pi + alpha)/2)
  	center = p1 + normalized_v1_perp*R 

  	d = distance between wheels
  	V = norm(v2)
  	omega = V/R
  	V_r = omega*(R + d/2)
  	V_l = omega*(R - d/2)

  	r = wheel_radius
  	w_r = right wheel speed = V_r/r
  	w_l = left wheel speed = V_l/r
