# Self-driving Car

This repository documents the self-driving car we assembled and programmed to compete in USC Viterbi's [Race On](https://minghsiehece.usc.edu/race-on/) competition in April 2019. 

**About Race On**

Race On is an event organized by the Ming Hsieh Department of Electrical Engineering at USC. It is directed primarily towards graduate students who were interested in practically applying concepts in image processing and control systems. The competition attracted participation from 43 teams, of which ours placed 8th.

**Track**

The setup was a black track made of foam, which had three thick white stripes taped onto it. One challenge we faced was that the camera was not high enough to capture all three stripes at once - it would usually see only the middle stripe, or, if it was in the middle of a turn, two stripes at most.

**Car**

We worked with the Sakura X1 Sports Nu car.

**Preliminary setup**

1. SSH into the Pi<br/>
<code>ssh pi@raspberrypi.local</code>

2. Enter the virtual environment<br/>
<code>source /raceon/bin/activate</code>

3. Run the Initialization Script<br/>
<code>bash init_script.sh</code>

4. Check if the motors are enabled and working<br/>
<code>python start.py</code>

5. Stop the running motors<br/>
<code>python stop.py</code>

6. Run the car<br/>
<code>python run.py</code>

**Control algorithm**

Another challenge we faced was the control algorithm to use. We eventually used a PID algorithm once we realized its performance could be quite good if the parameters P, I, and D were set correctly. The error component of the PID controller was the distance between the centre of the detected stripe and the calibrated correct centre of the track. This distance-based error was then used to calculate the adjustment for how the car's wheels should turn.

**Direction and speed control**

To adjust the direction of the wheels, we used the pwm1 parameter of the motor with the [pwmpy](https://github.com/scottellis/pwmpy) Python class. To adjust the speed, we used the pwm0 parameter. Since it was a race, the intention was for the car to go faster during straight segments, when the error was comparably less, and to slow down at turns so that it wouldn't miss a turn. We controlled the speed with a threshold for the error. 90 degree turns were easy to take, but a U-turn (180 degrees) proved to be challenging. Too fast and the car would miss the turn and go awry; too slow and the car would come to a halt.

**My contribution**

For this project, I was mostly involved in programming. I ensured that we split our task into small milestones and met regularly to track our progress. We mostly worked in pairs, and explained our logic and code to the other pair to test that our train of thought was rational. We actively worked on this project from February to April 2019, with April 12, 2019 being the date of the final race. 

In order, we assembled the car, learned about the function of each hardware component, understood how to use PWM for direction and speed control, captured an image using a RaspberryPi, then detected peaks (white stripe on black track) in the captured images, added the PID class to our code, adjusted the PID parameters, implemented speed control, and added cases to deal with multiple peaks being detected (such as in the start line, or during a turn). From there, it was mostly testing different PID parameters on the track and ensuring that it could complete any kind of turn. 

**Team**

Kriti Jain\
Prahalathan Sundaramoorthy\
Shyam S Ravikumar\
Veena Vijai


