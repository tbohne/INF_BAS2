# Modeling Mobility

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
- provide accurate information (especially when they involve a large number of participants
  and an appropriately long observation period)

### synthetic

- new network environments are not easily modeled if traces have not yet been created
- attempt to realistically represent the behaviors of MNs without the use of traces

## ENTITY MOBILITY MODELS

### RANDOM WALK

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
