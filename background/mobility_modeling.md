# Modeling Mobility

A mobility model is designed to describe the movement pattern of mobile
users/devices, and how their location, velocity and acceleration change over time.

- generate artificial movement that can be reproduces at any time
- performance of a wireless communication system often depends on the
  characteristics of the movements of the mobile nodes
- desireable to emulate the movement pattern
- otherwise simulation results may be misleading

In performance evaluation of a protocol for an ad hoc network,
the protocol should be tested under realistic conditions:
- sensible transmission range
- limited buffer space (for message storage)
- representative data traffic models
- realistic movements of the mobile users (mobility model)

Survey of mobility models that are used in the simulations of
ad hoc networks.

## ENTITY MOBILITY MODELS

- represent mobile nodes whose movements are independent of each other

## GROUP MOBILITY MODELS

- represent mobile nodes whose movements are dependent on each other

## Goal of the paper

- offer researchers more informed choices when they are deciding on a mobility
  model to use in their performance evaluations

- illustrate how the performance results of an ad hoc network protocol
  drastically change as a result of changing the mobility model

## Intro

- to simulate a new protocol for an ad hoc network, it is imperative to use a mobility
  model that accurately represents the mobile nodes
- mobility model should attempt to mimic the movements of real MNs (we would not want
  MNs to travel in straight lines at constant speeds throughout the course of the entire
  simulation because real MNs would not travel in such a restricted manner)

## TWO TYPES OF MOBILITY MODELS

### trace based

- observed in real-life systems
- networks have to exist
- based on user movement traces
- provide accurate information (especially when they involve a large number of participants
  and an appropriately long observation period)

### synthetic

- new network environments are not easily modeled if traces have not yet been created
- attempt to realistically represent the behaviors of MNs without the use of traces
- represent movement in a "realistic" fashion
- 4 types of models: random, temporal dependencies, spatial dependencies, geographic restrictions

## MOBILITY METRICS

- pure movement metrics: no further assumptions
- range-based metrics: contain a range around the ndoe as one parameter
- link-based metrics: depend on links between two nodes

## ENTITY MOBILITY MODELS

### RANDOM WALK

- nodes move to a randomly chosen destination with a randomly selected velocity
- first described mathematically by Einstein in 1926
- since many entities in nature move in extremely unpredictable ways,
  the Random Walk Mobility model was developed to mimic this erratic movement
- randomly choosing a direction and speed in which to travel (both chosen from predefined ranges)
- when it reaches a simulation boundary, it bounces off the simulation border with an angle
  determined by the incoming direction
- widely used mobility model which is sometimes referred to as Brownian Motion
- memoryless mobility pattern (no knowledge concerning past locations and speed)
- current speed and direction independent of its past speed and direction
- can generate unrealistic movements such as sudden stops and sharp turns

### RANDOM WAYPOINT

- each node starts from random position
- travels to randomly chosen destination (x, y)
- with a constant velocity chosen randomly from [0, v_max]
- bounces if boundary is reached
- includes pause times between changes in direction and/or speed
- MN travels toward the newly chosen destination at the selected speed
- upon arrival, the MN pauses for a specified time period before starting the process again
- similar to the random walk model when pause times are 0
- appropriate parameters need to be evaluated

### RANDOM DIRECTION

- created to overcome density waves (clustering of nodes in one part of the simulation area)

### MODIFIED RANDOM DIRECTION

- no longer forced to travel to the simulation boundary before stopping to change direction
- instead, an MN chooses a random direction and selects a destination anywhere along that direction of travel

### BOUNDLESS SIMULATION AREA

- relationship between previous direction of travel and velocity
  of an MN with its current direction of travel and velocity exists
- different in how the boundary of a simulation area is handled
- in all mobility models previously mentioned, MNs reflect off or stop
  moving once they reach a simulation boundary
- MNs that reach one side of the simulation area continue traveling
  and reappear on the opposite side of the simulation area
- this technique creates a torus-shaped simulation area allowing MNs to travel unobstructed

### GAUSS-MARKOV

- affected by its movement history --> temporal dependencies
- designed to adapt to different levels of randomness via one tuning parameter
- ensure that an MN doesn't remain near an edge of the grid for a long period of time,
  the MNs are forced away from an edge when they move within a certain distance of the edge

### PROBABILISTIC VERSION OF RANDOM WALK

- probability matrix to determine the position of a particular MN in the next time step
- produces probabilistic rather than purely random movements, which may yield more realistic
  behaviors
- e.g. rarely do we suddenly turn around to retrace our steps
- and we almost never take random steps hoping that we may eventually wind up somewhere relevant to our tasks

### CITY SECTION

- simulation area is street network that represents a section of a city where that ad hoc network exists
- streets and speed limits are based on the type of city being simulated
- MN begins the simulation at a defined point on some street
- then randomly chooses a destination
- movement algorithm from the current destination to the new destination locates a path corresponding
  to the shortest travel time between the two points
- save driving characteristics such as a speed limit and a minimum distance allowed between any MNs exists
- reaching the destination, the MN pauses for a specified time and then randomly chooses another destination
- provides realistic movements for a section of a city since it restricts the traveling behavior of MNs
- all MNs must follow predefined paths and behavior guidelines (e.g. traffic laws)
- in the real world, MNs do not have the ability to roam freely without regard to obstacles and traffic regulations

## GROUP MOBILITY MODELS

- models that represent multiple MNs whose actions are completely independent of each other

### EXPONENTIAL CORRELATED RANDOM MOBILITY

- motion function is used to create MN movements
- not easy to create a given motion pattern by selecting appropriate values

### COLUMN MOBILITY

- useful for scanning or searching purposes

### NOMADIC COMMUNITY MOBILITY

- just as ancient nomadic societies moved from location to location,
  the Nomadic Community Mobility model represents groups of MNs that collectively
  move from one point to another
- individuals maintain their own personal space where they move in random ways
- each MN uses an entity mobility model (e.g. Random Walk) to roam around a given reference point

### PURSUE MOBILITY

- attempts to represent MNs tracking a particular target
- could represent police officers attempting to catch an escaped criminal

### REFERENCE POINT GROUP MOBILITY

- random motion of a group of MNs as well as the random motion of each individual MN
  within the group
- group movements are based on the path traveled by a logical center for the group
- both the movement of the logical center for each group, and the random motion of each
  individual MN within the group, are implemented via the Random Waypoint Mobility model
- MNs do not use pause times
- pause times are only used when the group reference point reaches a destination
  and all group nodes pauses for the same period of time

## IMPORTANCE OF CHOOSING A MOBILITY MODEL

- choice of mobility model can have significant effect on the performance
  investigation of an ad hoc network protocol

## CONCLUSIONS

- performance of an ad hoc network protocol can vary significantly with different mobility models
- performance of an ad hoc network protocol can vary significantly when the same mobility model is
  used with different parameters
- selection of a mobility model may require a data traffic pattern that significantly influences protocol performance
- performance of an ad hoc network protocol should be evaluated with the mobility model that most closely
  matches the expected real world scenario
- since the development of ad hoc networks is relatively new, we do not yet know what a realistic model
  is for a given scenario
- if the expected real world scenario is unknown, researchers should make an informed choice
  about the mobility model to use

## SUMMARY FOR SYNTHETIC ENTITY MOBILITY MODELS

### RANDOM WALK MOBILITY

- with a small input parameter (distance or time) produces
  Brownian Motion --> basically evaluates a static network
- a large input parameter (distance or time) is similar to the Random Waypoint Mobility model
  without pause times
- main difference between these two: MNs are more likely to cluster in the center of the
  simulation area with the Random Waypoint Mobility model

### RANDOM WAYPOINT MOBILITY

- used in many prominent simulation studies of ad hoc network protocols
- appears to create realistic mobility patterns
- for example in a conference setting or museum

### RANDOM DIRECTION MOBILITY

- unrealistic model because it is unlikely that people would spread themselves evenly
  throughout an area
- unlikely that people will only pause at the edge of a given area
- the Modified Random Direction model allows MNs to pause and change directions
  before reaching the simulation boundary

### BOUNDLESS SIMULATION AREA MOBILITY

- movement patterns that one might expect in the real world
- only model that allows MNs to travel unobstructed in the simulation area
- undesired side effects that would occur from allowing the MNs to move around a torus

### GAUSS-MARKOV MOBILITY

- also provides movement patterns that one might expect in the real world
  (if appropriate parameters are chosen)

### PROBABILISTIC RANDOM WALK MOBILITY

- also provides movement patterns that one might expect in the real world
- choosing appropriate parameters for the probability matrix may be difficult

### CITY SECTION MOBILITY

- appears to create realistic movements for a section of a city

## SUMMARY FOR SYNTHETIC GROUP MOBILITY MODELS

### EXPONENTIAL CORRELATED RANDOM MOBILITY

- appears to theoretically describe all other mobility models
- selecting appropriate parameter values is (almost) impossible

### COLUMN, NOMADIC COMMUNITY AND PURSUE MOBILITY

- useful for specific realistic scenarios

### RPGM (REFERENCE POINT GROUP MOBILITY)

- generic method for handling group mobility
- correlated to the movement of other nodes

## SUMMARY

- if group mobility model is desired, using RPGM with appropriate parameters is recommended
- if entity mobility model is desired, using either Random Waypoint, Random Walk
  (if clustering is undesired) or Gauss-Markov is recommended
- further research on mobility models for ad hoc network protocol evaluation is needed
- devote further effort in examining the movements of entities in the real world
  to produce accurate mobility models
- further effort to develop new model that combines the best attributes of some of the models
- develop a minimum mobility model standard for performance evaluation
