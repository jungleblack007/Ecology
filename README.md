Ecology
=======

A fictive ecology where species are speciating/extinguishing at a rate specified by Metropolis-Hastings algorithm.

The program represents a fictive ecology with a specific charge capacity and containing ecologic events (speciation or extinction of a specie) located in a specific niche of this ecology at a specific time.

Species are clamped in right from the start. The creation itself of these species is a speciation event, and will always be a real ecologic event.
Then speciations/extinctions are proposed and accepted at a semi-random rate expressed by the Metropolis-Hastings algorithm.

The package consists of 7 classes in which 1 super class (EcoEvent) represents a simple ecologic event.
4 classes inherit from EcoEvent: FirstEcoEvent, representing events that can potentialy be choosen as the root of the whole tree, SpeciationEvent, ExtinctionEvent and LastEcoEvent, 1 per niche and representing ecologic events at the present, when time = 0.

Ecology, the main class of the project, has in its own main method an infinite while loop (it is wanted) in which SpeciationEvent and ExtinctionEvent are proposed.
Sub methods are instanciating the SpeciationEvent/ExtinctionEvent, and the move is accepted according to the Metropolis-Hastings algorithm and on whether or not the clamped clade has changed (if it did, the move is rejected).

Sub methods also propose, again according to Metropolis-Hastigs algorithm, to change the rate of speciation/extinction/niche activation and the niche and time of the root.
Here again, any change in the clade makes the move rejected.

To decide if a niche is occupied and if an EcoEvent is real, after each proposition of move the whole ecology is scanned. The method decideIfReal() is called on each node of the EcoEvent list.
