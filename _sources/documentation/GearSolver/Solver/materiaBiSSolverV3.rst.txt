materiaBiSSolverV3()
====================

This is the third iteration of the materiaBisSolver function. This function optimizes the materias of a gear set givne certain parameters.

You can find more information about the algorithm on the official github repository.


* Set : GearSet - GearSet to optimize
* matGen : MateriaGenerator - Materia Generator to use. Will use this materia generator to append materias to the gear set.
* matSpace : list[int] - list of Materias to consider when oversaturating and removing. The list contains the Stat.StatType values to consider.
* gcdTimerTierFight - Dictionnary of different GCD timer and the given Fight object. Maps a gcdTimer to a fight object where the player has the given gcd timer (the fight has been prebaked).
* hasteAmount : int - possible haste a player can received. Affects GCD timer.
* JobMod : int - Value of the JobMod of the player the Gear Set is on.
* IsTank : bool - True if the player is a tank
* IsCaster : bool - True if the player is a caster
* PlayerIndex : int - Index of the player in the Fight's PlayerList
* percentile : str - Percentile to optimize. "exp" is Expected.
* randomIteration : int - Number of time to run random simulations. (NO LONGER WORKS. LEAVE AS DEFAULT OR 0)
* mendSpellSpeed : bool - If true the algorithm will add SpS materias and not SkS
* maxSPDValue : int - Maximum Speed value for the Gear Set with melds.
* minSPDValue : int - Minimal Speed value for the Gear Set with melds.
* oversaturationIterationsPostGear : int - Number of times the algorithm will oversaturate the gear set.
* findOptMateriaGearBF : bool - If true means we are solving materias for every possible gear set/food. So this simply mutes the ProgressBar usually present.
* swapDHDetBeforeSpeed : bool - If True, the solver will swap DH and Det before swapping melds with Speed materias. If False it swaps after.
* minPiety : int - Minimum Piety value for the gear set. Default to 390

**Returns**

This function returns the found optimal gear set (with melds), 0 and an empty dict (GearSet, int, dict). The 0 and empty dict are for support of older code.

**Usage**

See code in BiSSolver for examples.