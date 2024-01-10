### Title slide

Thank you so much for introducing me...

Welcome to my presentation. As you could see on the screen, the proposed topic of my diploma is an adaptation of intertial navigation systems in robot's positioning system. Basicilly, this topic should be understood as an attempt to make an integrated positioning system based on inertial sensors and concepts taken directly from aviation.

### Agenda

And here is the agenda for today's presentation. Firstly I would like to say about motivation, aims of this thesis and  more about the project, that is strictly connected to. Next I will tell more about the actual state of knowledge, problems thats I'm already aware of and about same tests I already conducted to check if it even possible to be done. At the end of this presentation I would like quickly sum up what I'm planning to do, answer eventual question, if they appear.

### Motivation
For almost a year I participate in project that is realized here, in our division. Briefly, the aim of this project is to create new, hybrid methods to analyze overconstrainted multi-body systems. In this project, I am responsible for the preparation of experimental tests to prove our hypothesis. On the slide you can see the concept of the test bed we planned to build. This is the same device that you could see on Maximilian and Paweł's slides two weeks ago.

In the end, thanks to Professor Wojtyra, Dr. Mianowski and Pękal, the system was designed in CAD software, and the prototype was made as my intermediate project.
But there is the small. In a nutshell, the device is fully equipped with axial force sensor in every rod, but there is any position and orientation measuring sensor in this stand. If we wanted to measure force in dynamic, it's important to have position and orientation data correlated to this measures.

And this is the point at which my work kicks in. I plan to design smartphone-shape measuring system, that can be put on this platform, connect sensors and computer, and be able to estimate coordinates of the plaform when it move. As the core of this system I plan to use inertial navigation system with same modification. The most important modification is that as the platform has less that 6 DOF and move only in specific way I can use this information in my system. As a side effect of my work I would like to review more information about sensors, filtration and aggregation data, and about sensor fusion methods. The priorities of aims is not set yet.

### Sensors
And with that being said, lets go further to the state of knowledge. In navigation many sensor are used but the most common and basic are:

accelerometers that measure linear acceleration,
gyroscopes that measure angular velocity, and sometimes orientation,
magnetometers that measure magnetic field to get yaw angle, but in this application they are not really useful,
Global Navigation satellites system like GPS or Galileo, that again can not be used in this scale.
Rangefinder that measure distance, that may have an aplication, and let say that all kind of distance sensor in general.

### Sensors errr

Basically non of this sensor is infinity fast and precise. Every sensor measures with error. This error may but connected with bad mount, that we can fix, but more likely its just the precision of sensor alone. And the most significant components of sensor error are noise, usually with high frequancy and bias, constant by definision.

The senstensys that I would like you to remember are that sensors have finaite resolution and sampling time. Bias is especially harmful if measurements are integrated. And thats in this case. We want position and to get is, acceleration must be integrated even twice.

### Data filtation and sensor fusion

But there are some method to fight with errors. the common approach is to filter the measures. Many conventional filter are known, High freq filter, low frequation filter, notch filter, smoothing filter and so on. But there are also other method like oversampling, and adaptive methods.

The result of measures only is not the estimation of position & orientation. To get it, we need method to connect this measures and validate them each other. This method are called the sensor fusion. So in the simplest aproach to get position any fusion is needed, we can just integrate twice measures from accelemeter. To obtain orientation Complementary filter or Direct cosine matrix method can be used, based on accelormeter and gyroscope only. But the result of the methods are rather poor. 

### Kalman

The classical method to get them both is to use Kalman filter and trust the statisic. The kalman filter, especially in its extended from is universal math tool to estimate the most propable state, based on measures. To acheive that filter work in two phases: firstly it predict the next state and in second state it make correction, and again and again

### Kalman with constraints

But as I said at the beginning limitation of the mechanism, and way its move. So I found the consepct, proposed by Profesor Dan Simon from Cleverland, Ohio, who proposed to add the third phase to kalman filter. In this phase constraints are checked, and same kind of nonlinear function solving method are used to make the state of filter to apply with them.

And to check it, I made a simulation, as a project for other subject, where platform could move only horiziontally. I simulated sensors and Kalman filter and get this reasult without ckecing constrains: On this plot dark yellow and i guess magenta are X and Y coordinates of platform. As you can see the estimation drift, pink line go down in negative part, when the yellow go slowly up. And then when for the same configuration i turned on the constraints check, the estimation where way more close to position of platform. Some artefacts appear, but its doesnt matter at now.

### Summary

To conclude, as the exprected results of this thesis is to gather wide information about position & orientaion measurement systems. And to design the prototype.
It's not a secret that I'm quite inspired by the flight controller like this, which have most of the sensor and microcontroller inside. I would like to construct device quite similar to this, but to be used in robotic.

So that's it. If you have any question I'm here to answer them!


