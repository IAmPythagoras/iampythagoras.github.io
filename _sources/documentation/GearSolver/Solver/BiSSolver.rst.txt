BiSSolver()
===========

Finds the BiS of the player given a Gear search space and a Fight. The Solver will output to a file named bisSolver[Job]Result[number].txt with all the relevant information and returns the gearSets. 

The solver outputs the best Expected Damage GearSet. The solver requires at least one piece of every possible slots.

Note that is is possible to give a "prebaked" BiS by only giving 1 choice for some pieces and that it is also possible to add materias to the pieces in the GearSpace before running the solver. 

It is also recommend to have useNewAlgo set to true in order to use the faster and more efficient algorithm.

If you are solving for the Expected Damage BiS it is also recommend to have findOptMateriaGearBF set to True in order to try
every possible gear set as otherwise the best meld is only found once a gear set is found.

.. warning::

    Optimizing random gear sets hasn't been worked on for a bit. Assume only 'expected damage' optimization is working.

**Parameters**

* Fight : Fight - Fight object.
* GearSpace : dict - Dictionnary filled with the different gear pieces the algorithm can search through. Must have at least one of each gear types
* Materiaspace : list - List of all the stats the solver will look through when optimizing melds. Must be at least 3 materias
* FoodSpace : list - List of all food to look into. Must be non-empty
* PercentileToOpt : list - List of all gearset to optimize. Exp means to optimize expected damage. SHOULD BE LEFT AS "exp" ONLY.
* materiaDepthSearchIterator : int - Depth for which the Materia optimization searches into per step. (This feature is disabled. Left as default or 0)
* randomIteration : int - Number of times the solver will simulate random runs. Must be at least 100. (This feature is disabled. Leave at 100).
* oddMateriaValue : int - Stat gained from odd Materia.
* evenMateriaValue : int - Stat gained from even Materia.
* PlayerIndex : int - Index of the player for which the user wants to optimize the gearset. Must be the index of the player in the Fight.PlayerList.
* PlayerID : int - ID of the player for which we want to optimize.
* mendSpellSpeed : bool - If True the solver will look at Spell Speed value for speed.
* maxSPDValue : int - Max Spell Speed or skill Speed value. Every gear set above that value will be discarded.
* minSPDValue : int - Min Spell Speed or skill Speed value. Every gear set under that value will be discarded.
* useNewAlgo : bool - If set to true will use V3 of materiaBiSSolver. ALWAYS USE THIS.
* oversaturationIterationsPreGear : int - Number of times the algorithm will oversaturate gear before looking for best gear set
* oversaturationIterationsPostGear : int - Number of times the algorithm will oversaturate gear before looking for best materias
* findOptMateriaGearBF : bool - If true solver will find best gearset/food/melding using given algorithm. Only recommended for Expected.
* swapDHDetBeforeSpeed : bool - If True, the solver will swap DH and Det before swapping melds with Speed materias. If False it swaps after.
* minPiety : int - Minimum required Piety value for the set. By default set to 400.
* gcdTimerSpecificActionList : dict - Dictionary with key (gcdTimer, hastedGCDTimer) where the key maps to a list of actions to perform for the given gcdTimer and hastedGCDTimer. If is empty we ignore and only use the action list present in the fight object. Recommended to use the findGCDTimerRange() function with required minSPDValue and maxSPDValue in order to get an accurate dictionary. The mapping of gcd Tier does not have to be exhaustive. If no key is found it will use the rotation of the Fight object instead.
* saveAsFile : bool - If true saves the result in a file.
* showBar : bool - If true shows loading bar. If false doesn't but still updates the loading bar's memory
* loadingBarBuffer : dict - This dictionnary will be given the progress bar's adress at the key 'pb'. Can be used to access the PB.
* returnGearSet : bool = True - If true returns the gear set,random,text. If false returns the expectedDPS,text

**Returns**

Returns the optimalGearSet, optimalRandomGearSet and text result (GearSet, dict[str : GearSet], str) if returnGearSet = True and returns curMaxDPS and text (float, str) otherwise. This function also saves the text results as a .txt file.

**Usage**


.. code-block:: python

    from ffxivcalc.GearSolver.Gear import ImportGear, Food
    from ffxivcalc.GearSolver.Solver import BiSSolver, getBaseStat, getGearDPSValue

    GearSpace = ImportGear("BLMSet.json")

    HD = Food({"DH" : [103, 0.1], "Det" : [62, 0.1]}, "Honeyed Dragonfruit")
    DB = Food({"SkS" : [103, 0.1], "DH" : [62, 0.1]}, "Dragonfruit Blend")
    BG = Food({"Crit" : [103, 0.1], "SkS" : [62, 0.1]}, "Baba Ghanoush")
    BE = Food({"Det" : [103, 0.1], "Crit" : [62, 0.1]}, "Baked Eggplant")
    CW = Food({"SS" : [103, 0.1], "DH" : [62, 0.1]}, "Caviar Sandwich")
    CC = Food({"Crit" : [103, 0.1], "SS" : [62, 0.1]}, "Caviar Canapes")
    MB = Food({"Ten" : [103, 0.1], "Det" : [62, 0.1]}, "Marinated Broccoflower")
    BS =  Food({"Det" : [103, 0.1], "Ten" : [62, 0.1]}, "Broccoflower Stew")
    #foodSpace = [CC, CW, BE, HD]
    foodSpace = [BE]

    Crit = 0
    DH = 1
    Det = 2
    Ten = 5
    materiaSpace = [Crit, DH, Det]
    optimal, random, text = BiSSolver(Event, GearSpace,materiaSpace, foodSpace,PercentileToOpt=["exp"], randomIteration=100, mendSpellSpeed=True,minSPDValue=800,maxSPDValue=900, useNewAlgo=True, 
                                oversaturationIterationsPreGear=1, oversaturationIterationsPostGear=1,findOptMateriaGearBF=True,swapDHDetBeforeSpeed=True, minPiety=0)