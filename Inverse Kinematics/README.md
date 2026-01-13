<h2>Final Report</h2>

<p align="justify">
One of the main challenges in this lab was correctly implementing the analytical inverse kinematics for a three-link manipulator. Managing the coordinate system and making sure the end-effector accurately reached the desired (x,y)(x, y)(x,y) position required careful mathematical simplification. Because the orientation of the third link depends on the first two, an effective target point (x′target,y′target)(x′_{target}, y′_{target})(x′target,y′target) was first calculated by assuming an initial orientation using atan2(ytarget, xtarget). Converting these geometric concepts into functional JavaScript code demanded precise use of Math.atan2 to handle angle calculations correctly in all quadrants.
</p>

<p align="justify">
Another major difficulty was handling edge cases, particularly when the user-specified target was beyond the robot’s reachable workspace. This was solved by adding a validation step that compared the distance d to the effective target with the sum of the first two link lengths (l1+l2)(l_1 + l_2)(l1+l2). If the target was unreachable, the program displayed an error message and prevented the arm from moving. Furthermore, the Law of Cosines calculations for θ1\theta_1θ1 and θ2\theta_2θ2 required careful adjustment to ensure the arm’s visualization updated correctly each time the “Move to Target” button was pressed.
</p>
