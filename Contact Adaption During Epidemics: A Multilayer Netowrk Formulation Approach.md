# CHALLENGES
# INTRODUCTION
# NOTE
# REFERENCES
# RELATED WORK
# REQUIREMENTS
# KEY CONTRIBUTION
# WHAT HAVE WE DONE
# CHALLENGES
# TERMINOLOGY
# STANDARD AND BASELINE
# METHODOLOGY

Though the following papers are not implemented for time series forecasting, it provides ideas of 
how epidemic networks can be constructed in which predictive model can be on.
Compartmental model can be constructed as a network for dynamical graph simulation.
Sahneh et al.\cite{sahneh2017contact} purposed a multilayer network construction of AC-SAIS markov model.
Disease dynamics components of the AC-SAIS model is according to the network SIS model. 
SAIS model consists of four competing stochastic transitions including: Infection of susceptible nodes,
Alerting of susceptible nodes, infection of alert nodes, recovering of infected nodes.
Each node can be in 3 possible states: susceptible, alert and infected state.
A node state change from susceptible to alert when a node acknowledge that it had been in contact with infected 
nodes in the past.
The paper constructed AC-SAIC markov model with directed multilayer network.
The multilayer network contains 2 types of networks, which are connected by different edges types, including 
susceptible networks and alert networks.
Alert network is a network that is formed when a node change states from susceptible state to alert state.
Similarly, susceptible network is formed when nodes are in susceptible state. (contact within a normal social
circle)
Take for instance the contact between node i who is a nurse, and node j, who is a student. 
These two might not have any social contact in normal situation (susceptible networks), however, when node j
(the student) is sick, she can possibly pass infection to node i ( the nurse); and this is the contact
important for epidemic modeling purpose.
Also realize that this contact is directional because when the nurse is sick she may not have physical contact
with student. 
Such contact adaptation scheme is most sensible when the identity of infected contacts are not known to the
individual.
In the case of COVID19 pandemic, lockdown individual or hospitolized patient are considered to be in alert 
state. 
# RESULT
# FREQUENCY ASK QUESTION
