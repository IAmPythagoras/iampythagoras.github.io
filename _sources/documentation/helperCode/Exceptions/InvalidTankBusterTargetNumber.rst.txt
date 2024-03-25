InvalidTankBusterTargetNumber
=============================

This exception is raised when an event is defined as a tank busterbut has an invalid number of targets. Tank buster's number of targetsmust be 1 or 2. This error will be raised only if the Event has its "experimental" flag set to false (false by default). It must be, in any case, a positive value.