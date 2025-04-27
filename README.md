# Autonomous-Propulsion Robot

Robot:

![Image](https://github.com/user-attachments/assets/93434f51-44bd-41b7-94bb-3b5656512eef)
![Image](https://github.com/user-attachments/assets/c55a7e60-f2d1-42f6-a7db-17c0151b9f64)
![Image](https://github.com/user-attachments/assets/1b92e3d2-68f4-42bd-877a-42906026e93f)

Mechanical Design
For our autonomous rover, the first mechanical challenge was designing the steering system. We chose an Ackerman steering system powered by a mounted servo to reduce slippage and ensure accurate turning. In SolidWorks, we carefully modeled the steering arms with precise angles to create the correct turning radius difference between the inner and outer wheels. To build the chassis, we used lightweight laser-cut plywood, ensuring it was durable yet minimal in weight for optimal performance.

The second primary design goal was the propulsion system, where we utilized a unique rack and pinion mechanism with a one-way bearing. This system allowed the robot to move forward by harnessing the outward stroke of the piston, ignoring its retraction. We designed the rack and pinion in SolidWorks with precise gear teeth profiles to ensure smooth meshing and efficient power transfer, carefully calculating the gear ratio and travel distance.

Our design stood out because of its stability. The servo-powered steering mechanism minimized sources of friction, providing smooth and responsive handling. The Ackerman steering further reduced slippage, allowing the robot to maneuver effectively by ensuring the inner and outer wheels followed distinct radii. Additionally, we placed the electronics and propulsion system near the robot's base to keep the center of mass low, which increased stability. The spread-out wheels provided ample ground contact area, ensuring better grip and less sway. Thanks to these design features, the robot maintained consistent forward motion with no wobbling, setting it apart from others.

CAD Model:

![Image](https://github.com/user-attachments/assets/7ad23d01-5027-4530-a0cf-face75efc11d)
![Image](https://github.com/user-attachments/assets/16d1a6ee-cb1c-4af5-9d1e-4cd74763c7be)
![Image](https://github.com/user-attachments/assets/bb04466d-6fff-4fcc-9279-096ce6406476)
![Image](https://github.com/user-attachments/assets/ed27c3f6-52cc-4924-abbe-4ecb841b1b9f)

Software Design
In terms of software, the first design goal was real-time adaptive steering. We implemented a proportional-derivative (PD) controller to adjust the robot’s heading and keep it as centered as possible, similar to how a human VOR (Virtual Omnidirectional Receiver) works. The PD controller allowed the robot to follow a heading while responding to changes in orientation. The system also handled deviations caused by mechanical imperfections, external forces, or environmental factors, ensuring the robot stayed on course.

Additionally, we integrated distance tracking using a limit switch. This switch counted wheel rotations, enabling us to track how far the robot had traveled. Using this data, we could program the robot to turn at precise points, ensuring it stayed within the track boundaries and improved our scoring potential. By calculating the traveled distance, the robot could start turning at the right moment, as programmed.

We also took a unique approach to magnetometer data collection. To avoid interference from the solenoid, which generates a magnetic field when activated, we decided to take magnetometer readings only when the solenoid was off. This ensured more accurate heading data, allowing the robot to maintain its orientation and follow a straight path with better precision.

Experimental Testing and Optimization
For experimental testing, we focused on optimizing the accuracy of the robot. We varied the Kp value of the proportional controller to find the optimal setting. This parameter controls the servomotor’s response to changes in position. After testing five different Kp values over ten runs each, we found that a Kp value of 0.9 resulted in the smallest deviation from the center line, providing the highest accuracy. Although this was the best result, we decided to conduct further testing and adjusted the Kp value to 1.0 for final optimization, which was used in our final code during the competition.

To compare our robot’s performance to a theoretical model, we analyzed the impulse response of the robot. By collecting data from the limit switch clicks, we generated position and velocity plots for ten impulses. Although we faced some challenges with friction in the propulsion system, the experimental data still closely matched the predicted results from our simulator, which was programmed in MATLAB. The discrepancies we observed were largely due to the limited sensor resolution and the quantized data from the limit switch clicks.
