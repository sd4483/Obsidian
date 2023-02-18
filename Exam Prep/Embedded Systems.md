### Common Characteristics of Embedded Systems
#### Reliability
It should be reliable in diferent kinds of environments, with different kinds of inputs & functions. It shouldn't breakdow because of an unknown input.

**Functional vs Non-Functional requirements**: In the example of a camera, some non-functional requirements could be, speed, resolution, display, safety, etc and functional requirements could be, clicking a button and taking a picture.

**Unit testing**: Testing the individual component of a system

**Gajski's Y-Chart**: Breaking down the design process into 3 steps
	Behavioral: Functional vs Non-functional (High level of abstraction)
	Structural: Architecture
	Geometrical: Physical environment (Low level of abstraction)

**Model**: A model could be a simple sketch or a mockup that represents the characteristics and properties of the modeled entity. A good model is something that serves it's intended purpose. It abstracts away the details that are not needed.

The specification of a certain model or system is important cos then everyone can work on it. It's not limited to just a few entities.

**Requirements for Specification & Modelling:**
- Hierarchy (Humans cannot easily comprehed complex things. That should be taken into consideration when modelling behaviour)
- Component based design (systems designed from different components, sometimes adding new components could cause security issues)
- Timing (Elapsed time, delayed time, timeouts, deadlines)
- Support for designing reactive systems (state-oriented, event-driven, exception-oriented behaviour)
- Techniques(Executability, scale, complexity, domain-specific support, readability, etc)

**Specifications of Embedded Systems**: We may want to represent the behaviour of the system in different ways
- State-oriented behaviour (depends on the state - camera off / camera on)
- Event-handling (based on interactions or events both external and internal - button clicked)
- Exception-oriented behaviour (Something like, the system needs to arrive at a certain state despite the previous inputs or the state its currently in. Eg: Shutting down a computer maybe)

Automata is like a machine that has input, internal state and output.

**Classical automata**:
- Moore-automata: Output controlled by state. The next state is controlled by input and current state
- Mealy-automata: 
- In classical automata. So it can't deal with events or behaviours that require time as a trigger. If you are modelling a washing maching for example, you cannot do that using this cos there is no time trigger, we cannot say this process needs to execute for this much amount of time.

**Timed automata**: Automata + models of time
- In timed automata, there are clocks, usually represented by x or y, so on...
- Clocks initialized with zero (0) at the start of the system
- A process can be in a certain state for only some amount of time
- There are also constraints on the events, meaning that event can only happen if a certain condition is satisfied.
- There is a reset clock as well, sometimes when a state is changed, we may want to reset the state.

**How to approach the timed automata question:**
- Think about the events - Events are input from the sensors. In the bike example, on-off button pressed is an event, pedal turning is an event, brake-applying is an event
- Think about the states of the system - on/off state for whole system, motor on/off state for actuators, initial state, states not reachable from initial state
- Think about the clocks - timing requirements (motor-on never more than 3 seconds if not pedaling, bike turns off after 5 minutes if motor never turned on)

Where the requirement is translated into a constraint and the constraint maybe attached to some state, event or some transition. You have have as many clocks as you think need to be. Don't think too much about optimizing the number of clocks.

There is one clock for the whole system and there could be one clock for each actuator. 

I think whenever the clock or timing requirement is not used, it should be reset to zero. Especially when transitioning from one state to another, it has to be reset to zero.

First identify the different states the system could be in. If there are actuator, this could mean multiple states combined with system state. In the bike example, there are 4 states in total:
- System Off - Motor Off (Initial state)
- System On - Motor Off 
- System On - Motor On
- System Off - Motor On (Never reached stated also as mentioned above - 'state not reachable from initial state')

The problem with classical automata is that they are not good for representing complex systems. There maybe a lot of transitions, lot of events and states to reprent in a complex system and it will be hard for a user to comperehed what the system is doing by looking at the automata design.

That's when State Charts are useful.

If there is no history state, the system might go back to the default state from an exception state after a certain input is given. If we want the system to go back to the previous state the system was in when it left the super state, then a history state is required.

In Or-Super State, the FSM could be in any one of the basic states when the super state is active.

In And-Super State, the FSM could be in two basic states when the super state is active. This helps in modelling concurrency.

State charts are appropriate for local control systems, but not for distributed applications for which updating variables might take some time. 

**Pros of StateCharts:**
- Hierarchy allows arbitrary nesting of AND- and OR-super states.
- (StateMate-) Semantics defined in a follow-up paper to original paper.
- Large number of commercial simulation tools available (StateMate, StateFlow, BetterState, ...)
- Available “back-ends“ translate StateCharts into SW or HW languages, thus enabling software or hardware implementations.

**Cons of StateCharts:**
- Not useful for distributed applications,
- no program constructs,
- no description of non-functional behavior,
- no object-orientation,
- no description of structural hierarchy,
- generated programs may be inefficient.

**What is a model** - A simplification of a physical system, in this case an embedded system that we want to build/develop. It can also be a simplification of another model. This will really help us when we want to look at only certain aspects of the embedded system and simplification will help us focus on that. Different models serve different purposes, a model for a systems designer would be different from a model for business manager. 

With Petri Nets, the focus is not on computation, it's more of on the dependencies that happen in the system, especially on the resources. These resources could be power resources like battery, electricity, etc, and network resources, etc.

==**Condition Event Nets:**==
- Every Condition Event has **three components**
- One is a set of **conditions** (Circles)
- Another is a set of **events** (Rectangles)
- Last is the **Flow relation** between condition and event or event and condition
- Condition and Event are disjoint sets

The tokens in the initial places for petri nets are added based on weights. If the transition happening from that place has a weight of 3, then that place will have 3 tokens. If no weight is mentioned, then default 1 token will be added.

Condition Event nets focus on modeling casual dependencies, no global synchronisation assumed (message passing only)

==**Bipartite graph**== - Conditions, events and the flow relation form a bipartite graph (graph with two kinds of nodes)



