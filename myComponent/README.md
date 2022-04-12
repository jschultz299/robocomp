# MyFirstComp
This component was developed from following the RoboComp tutorials. This component operates on the simpleworld.xml evironment. The robot moves forward with constant velocity. When an obstacle is detected by the robot's laser, the robot rotates until the obstacle is no longer detected, then continues forward.


## Configuration parameters
As any other component, *MyFirstComp* needs a configuration file to start. In
```
etc/config
```
you can find an example of a configuration file. We can find there the following lines:
```
CommonBehavior.Endpoints=tcp -p 10000

# Proxies for required interfaces
DifferentialRobotProxy = differentialrobot:tcp -h localhost -p 10004
LaserProxy = laser:tcp -h localhost -p 10003

InnerModelPath = innermodel.xml

Ice.Warn.Connections=0
Ice.Trace.Network=0
Ice.Trace.Protocol=0
Ice.MessageSizeMax=20004800
```

## Starting the component

### 1) In a new terminal, start the rcnode:

```
rcnode
```

### 2) In a new terminal, navigate to the directory containing the simpleworld environment:
```
cd robocomp/files/innermodel
```
Then, load the simpleworld environment:
```
rcis simpleworld.xml
```

### 3) In a new terminal, navigate to the component's home directory:
```
cd robocomp/myComponent
```

Then, run the component:

```
bin/MyFirstComp config
```
