# amr_bma
Design of a BioModelAnalyzer (BMA) model to model the rise of antimicrobial resistance (AMR) in a host. Done as part of Part III (MSci) Systems Biology at the University of Cambridge.

This repository contains the target functions for all the nodes in the BMA model. 

The BMA model is made up of 6 'cells', 5 of which are specified above. The 6th cell - constants - is not specified as all its nodes are constants. In other 'cells', nodes which are constants are also not given. Here follows a list of nodes which are constants:
* antibiotic_chronometer > time_A
* antibiotic_chronometer > time_B
* constants > host_capacity
* constants > INIT
* constants > antibiotic_activation_threshold
* dormancy_chronometer > time_dormant
* resistance_chronometer > resA_time
* resistance_chronometer > resB_time

## Brief outline of what each 'cell' does

### antibiotics
Contains the two antibiotics - A and B
### antibiotic_chronometer
Allows user-defined control over how long the antibiotics are active in the system for, e.g. treatment duration. Controlled through time_A and time_B.
### constants
Contains miscellaneous constants
* host_capacity - places an upper limit on the total population of bacteria possible in the host. Considering this incoporates competition into the model.
* INIT - initialises the first strain (sus_A)
* antibiotic_activation_threshold - antibiotics are only activated (e.g. given to the patient) when the total population of bacteria has passed this threshold (e.g. when the infection has gotten severe enough to present symptoms and warrant treatment)
### dormancy_chronometer
Allows user-defined control over how long dormant strains are dormant for. Controlled through time_dormant.
### resistance_chronometer
Allows user-defined control over how long it takes for resistance to develop in a strain following sustained exposure to an antibiotic. Controlled through resA_time and resB_time.
### patient
Represents the host system - each node within the patient is a strain of bacteria.
