Fight.SimulateFight()
=====================

This function starts the simultion of the *Fight* object.

**Parameters**

* TimeUnit float - Unit at which the simulator will advance through time in the simulation in seconds.
* TimeLimit float - Time limit (at which the simulation will stop).
* vocal bool - True if we want to print out the results
* n : int -Amount of random simulation done to graph the DPS distribution.
* PPSGraph bool - True = If we want the PPS graph to be next to the DPS graph
* MaxTeamBonus bool - False = If true, gives the 5% bonus regardless of team comp
* showProgress bool - True = If true show fight progress bar. Still computes the Pb even if false.
* computeGraph bool - True = If true will process the Graphs even if they do not show.
* loadingBarBuffer = None = This dict will have the key 'pb' be set as the progress bar of the simulation.

**Return**

This function returns 3 values : (result string, fig, fig2). Fig 1 is a plot object of DPS Vs. Time while fig2 is a plot object of DPS Distribution.

**Usage**

.. code-block:: python

    # Usage
    newFight.SimulateFight(0.01 ,100 ,True ,PPSGraph = True, MaxTeamBonus = False, MaxPotencyPlentifulHarvest =False, n = 1000, showProgress = True, computeGraph = True, loadingBarBuffer = None)

    
