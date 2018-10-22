# Related Work

## Guidance

    In order toprovide more functionality and reduce the reliance on operator oversight, a robust obstacle avoidance capability must be added. Once the obstacle avoidance piece has been sufficiently demonstrated, then more advanced behaviors can be added, such as autonomous recovery in the case of lost communications, target tracking and/or interception, etc. [Larson2006Autonomous]

    A two-tiered obstacle avoidance approach has been adopted, consisting of a near-field or reactive OA component and a far-field or deliberative OA component that operate simultaneously and in conjunction with one another. The primary function of the deliberative component is to continuously modify the existing waypoint route to plan around obstacles detected with the long-range sensors. The reactive OA component is responsible for avoiding obstacles in close proximity to the vehicle regardless of the vehicle’s mode of operation or mission. [Larson2006Autonomous]

    Larson et al. base their deliberative OA on Nautical charts and their reactive OA on Raw Radar, Stereo Vision, Nautical Charts!?, Monocular Vision and Milimeter Wave Radar.

    Designing an obstacle avoidance system entails two architectures; (a) deliberative and (b) reflexive or reactive. The deliberative
    architecture includes all the fixed known obstacles or objects which are in the far field. By contrast, the reflexive architecture deals with (pop-up) objects that are too close to cause collision with the vehicle being operated [Naem2012COLREGs]

### Global/Deliberative

    1. The map for the deliberative OA component is filled with stationary obstacles from the chart server and moving obstacles provided by the radar in the form of Automated Radar Plotting Aid (ARPA) contacts. [Larson2006Autonomous]

    2. A*

    3. The proposed approach employs a simple waypoint by line-of-sight (LOS) guidance strategy [8] coupled with a manual biasing scheme. The vehicle is normally guided to stay on the direct LOS route between successive waypoints when no obstacles are found. This manual bias deviates the course of the USV and thus the obstacle is evaded. Once the threat is passed, the craft is again commanded to follow the direct LOS angle between its current position and the next waypoint.[Naem2012COLREGs]

    4. A circle-of-acceptance (COA) is also assumed around each waypoint which flags the arrival of the ship at each one. When the vehicle enters the COA of a waypoint, the mission planner selects the next waypoint and the vehicle is guided towards it. The COA is normally taken to be twice the length of the vessel being commanded [8]. [Naeem2012COLREGs]

    5.  Waypoint Guidance Based on the Line of Sight (LOS)

    Let the unmanned vehicle mission be given by a set of waypoint [ xd ( k ), yd ( k )] for (k=1...N). If the desired heading angle is only changed at each waypoint, some overshoot will be observed when waypoint is changed. An alternative algorithm to generate a smooth reference trajectory is given, named LOS [6]. Hence, the desired heading angle: After the quadrant check is performed with the desired heading angle, the next waypoint can be selected on a basis of whether the vehicle lies within a circle of acceptance with radius ρ0 around the waypoint [ xd ( k ), yd ( k )] . If the vehicle location [ x( t ), y( t )] at the time t satisfies:[Tran2014Tracking]


#### DPSS (Direction Priority Sequential Selection)
    
    The DPSS algorithm is essentially a modified version of the A* method which has been developed by Yang et al. [20] to enhance its performance in terms of improved trajectories and computational cost. DPSS method is based on a Goal Direction Vector and results in search time reduced by up to 50% when compared to traditional A*. [Naeem2012COLREGs]

### Local/Reactive
#### Obstacle Avoidance

    It is common to employ a virtual safety zone around the obstacles as well as the ship being controlled. These zones must not be breached at any time unless strictly necessary. Their sizes depend on the dynamics of the vessel but should be at least twice that of the vehicle’s minimum turning radius.[Naeem2012COLREGs]

    Here a circular safety zone2 called the circle-of-rejection (COR) is assumed around each obstacle. Note that the proposed algorithm is independent of the shape and size of the static object. [Naeem2012COLREGs]

    1. follows the original path as much as possible and avoids obstacles, both moving and stationary. It does this with the help of a path planner using a two-dimensional (2D) obstacle map. [Larson2006Autonomous]

    2. Obstacle map [Larson2006Autonomous]
        2.1 Ocuppancy grid
            2.1.1 created by dividing the environment into a discrete grid
            2.1.2 Assigning each cell location a value representing the probability of being occupied or not occupied by an obstacle
    
    3. Velocity Obstacle [Larson2006Autonomous]
        
        This algorithm transforms a moving obstacle into a stationary one by considering the relative velocity and trajectory of the USV with respect to the obstacle. After producing a collision area called the Velocity Obstacle, defined using the relative velocity vector, the algorithm returns a set of USV velocity vectors guaranteeing collision avoidance. This transformation and collision area detection, when applicable, reduces the complexity of the path planning among moving obstacles problem to linear time.
    
    4. Projected obstacle areas [Larson2006Autonomous]

    5. Potencial Fields
    5.1 Among the research of obstacle avoidance planning for USV, the implementation of Artificial Potential Field is most widely used.[Xie2014Obstacle]
        5.2 Its essence is identification of the abstract potential field which consists of the repulsion potential field of obstacles and gravitational potential field of targets in the operational space. [Xie2014Obstacle]


## Hybrid path planning

    1. We have developed an approach that utilizes a lattice-based trajectory planning to generate a dynamically feasible, resolution optimal, collision- free trajectory to allow the vehicle to reliably reach the motion goal. We utilized a trajectory following controller to achieve high tracking efficiency while still preserving motion safety. [Svec2012USV]

## Navigation

    The base functionality is waypoint navigation. Waypoint navigation without obstacle avoidance (OA), however, provides only limited capabilities to the warfighter in a real-world mission. [Larson2006Autonomous]

## Control

    The USV is equipped with an Inertial Navigation System (INS), which calculates inertial position, velocity, and attitude of the vehicle from data given by the IMU sensor. Because of INS accumulative errors resulting from inherent drift of deadreckoning velocities and integration of acceleration,an Extended Kalman Filter (EKF) algorithm should be developed, which utilizes a wide range of navigation sensors, to compensate for the accumulation in errors (attitude, position, velocity). The error state Kalman filter is composed of four blocks that are estimate error covariance, Kalman gain computation, update error covariance, and update estimate with measurement [8]. In general, after applying EKF algorithm, we can estimate reliable attitude, position, and velocity values that used to accurately navigate the vehicle [9]. [Tran2014Tracking]


## Sensing

## Larson - 2006 - Autonomous navigation and obstacle avoidance for unmanned surface vehicles

