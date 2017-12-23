# Some help on course material for intro to self driving cars



## Lesson 10: Robot Localization, Quiz: Inexact motion 2
This is the clip from udacity intro to self driving car. <br />
![Alt text](inexact-motion2/Seb_robot_motion.png?raw=true "the quiz")

Same thing in excel <br />
![Alt text](inexact-motion2/initial_pos.png?raw=true "the initial position")


Remember the world (cell) is cyclic. When robot is at cell 5, it can move back to cell 1 by taking a single step (C5 -> C1)

Also remember, the robot movement is not accurate which can make the robot fall short or overshoot its intended location.
Say robot wants to move from C2 -> C5, it can land in cell C3, C4,C5. We can quantify where it can land using probability distribution.

P(C4|C2) = 0.8 <br /> 
P(C5|C2) = 0.1 <br /> 
P(C3|C2) = 0.1 <br /> 

The robot final position will look like this: <br />
![Alt text](inexact-motion2/certain_world.png?raw=true "The certain world")

But, in the above world, we assume the robot knows it's location for Sure (C2), but in acutal world, knowing exact location is not always possible (nothing related to  [Heisenberg's uncertainty principle](https://en.wikipedia.org/wiki/Uncertainty_principle))

So, we need to represent the initial location of the robot with a probability distribution, hence <br />
![Alt text](inexact-motion2/initial_pos.png?raw=true "the initial position")

The robot believes its at cell 2 or cell 4 initially .
P(C2) = 0.5
P(C4) = 0.5

So, we need to find the final location given : <br />
1. The initial location of robot <br />
2. The uncertainity(below) associated with the moition <br />

P(two cells ahead | given the current cell) = 0.8
P(one cell ahead | given the current cell) = 0.1
P(three cells ahead | given the current cell) = 0.1

This problem can be broken down into two:
1. Assume the robot is at position C2, ignoring the C4 probability <br />
2. Assume the robot is at position C4, ignoring the C2 probability <br />
3. Adding up the result from step1 and step2 to find the total probability <br />

1. Assume the robot is at position C2, ignoring the C4 probability <br />
![Alt text](inexact-motion2/part2.png?raw=true "the initial position")

2. Assume the robot is at position C2, ignoring the C4 probability <br />
![Alt text](inexact-motion2/part1.png?raw=true "the initial position")

3.Adding up the result, we get the final answer. <br />