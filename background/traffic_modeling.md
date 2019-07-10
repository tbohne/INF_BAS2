# Traffic Modeling

As new communication services evolve, better models to predict system performance are required.

- efficient flow of information is key element in today's technology environments
    --> communication infrastructure (if properly designed and operated, invisible to end users)

- design and management decisions require predictions of network performance

### METHODS TO EVALUATE AND COMPARE NETWORK DESIGNS AND PROTOCOLS
- analytical techniques
- computer simulation
- projections from existing experience
- experimentation (often incomplete knowledge of user demands etc.)

## OVERVIEW OF COMPUTER SIMULATION MODELING FOR COMMUNICATION NETWORKS

Developing a simulation program requires:

- modeling random user demands for network resources (pseudo random number generators are used)
- characterizing network resources needed for processing those demands
- estimating system performance
- trade-off between model detail and simulation execution time

### DES (Discrete-Event Simulation)
- most tools for telecommunication networks are based on DES
- event-based processing
- typical event: arrival of demands for network resources

### TRAFFIC MODELING IS KEY ELEMENT IN SIMULATING COMMUNICATION NETWORKS

- most common modeling context is queueing
- simple traffic consists of single arrivals of discrete entities (packets)
- compound traffic consists of batch arrivals (more than one unit)
- simplest case: simulation needs to randomly generate a sequence of interarrival times
- in addition to arrival times and batch sizes, you may want / need to simulate workload

### CBR (Constant Bitrate)
- simple model
- number of packet arrival events per time unit
- packet size also constant
- easy to implement
- not realistic (however: VoIP and video transmission sometimes appear as CBR traffic)

### GENERATE TRAFFIC
- time may be discrete / continuous
- pseudo-random number streams
- different traffic streams --> different telecommunication services (voice, video, file transfer, ...) can be multiplexed to form a realistic mixture of traffic


### VBR (Variable Bitrate)
- video, where coded frames (arrivals) have variable and random size (bit rate)
- must be delivered deterministically every 1/30 of a second for high quality video


### TRAFFIC BURSTINESS
- traffic occurs in bursts
- e.g. by compressed video, file transfer, ...
- arrival points appear to form visual clusters
- can be explained by positive autocorrelations to a large extent
- expected to dominate broadband networks
- interarrival times: several short ones are followed by a long one

### RENEWAL TRAFFIC MODELS
- interarrival times are independent
- special cases: Poisson & Bernoulli

### POISSON PROCESSES
- oldest traffic models (renewal model)
- stochastic process that generates events with exponentially distributed interarrival times
- bursty and idle periods
- very close to real processes in telephone networks
- real network traffic is more bursty that Poisson traffic

### BATCH POISSON PROCESSES
- instead of single packets --> batches of packets
- generated traffic is more bursty that Poisson traffic
- still not really close to real load

### BERNOULLI PROCESSES
- discrete-time analog of Poisson processes

### PHASE-TYPE RENEWAL PROCESSES
- interarrival times are of phase type

### MARKOV AND MARKOV-RENEWAL TRAFFIC MODELS
- potentially able to capture traffic burstiness

### MARKOV-MODULATED TRAFFIC MODELS
- extremely important class of traffic models
- introduce an explicit notion of state into the description of a traffic stream

### MARKOV-MODULATED POISSON PROCESSES
- real network traffic cannot be accurately modeled with a fixed packet arrival rate
- combine simplicity of modulated Markov process with Poisson
- shows varying arrival rates
- still not sufficient to represent real network traffic

### HOW CLOSE ARE THESE LOAD MODELS TO REAL NETWORK TRAFFIC?
- real traffic is still more bursty than MMPP

### TRANSITION-MODULATED PROCESSES
- modulated agent is state transition, not a state per se

### FLUID TRAFFIC MODELS
- views traffic as stream of fluid (characterized by flow rate, e.g. bits per sec),
so that a traffic count is replaced by traffic volume

### AUTOREGRESSIVE TRAFFIC MODELS
- particularly suitable for modeling VBR-coded video
- the nature of video frames is such that successive frames within a video scene
  vary visually very little, only scene changes can cause abrupt changes in frame bit rate

### LINEAR AUTOREGRESSIVE MODELS

### TES MODELS (Transform-expand sample)

### RARE-EVENT SIMULATION

### SELF-SIMILAR TRAFFIC MODELS
- traffic appears to be statistically self-similar (structural similarities across all or
  wide range of time scale)
- in the case of packet traffic, self-similarity is manifested in the absence
  of a natural length of a burst: at every time scale, similar looking traffic bursts are evident
- LAN traffic is self-similar (looks roughly the same regardless which time scale is observed)

### TWO BUGS IN THE GARDEN
- not try to normalize all network measurements relative to some far away
  global long-term average value the system may never reach

### REALISTIC TRAFFIC?
- what is realistic traffic?
- which kind of traffic is used in the network modeled?
- which kind of applications are used?

### SOME NOTES

- Monte Carlo simulation provides a powerful generic modeling methodology for predicting the performance
- simulation models can be used in designing and managing communication networks
- diverse traffic mixes and burstiness of some services present formidable modeling challenges
- poor predictions lead to inappropriate design and management decisions (impacting users)
