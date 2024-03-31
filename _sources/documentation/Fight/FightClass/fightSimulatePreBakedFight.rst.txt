Fight.SimulatePreBakedFight()
=============================

This function simulates the damage done by the pre baked actions. The player ID with the pre baked actions must be given. 
The user must also specify all the damage values computed from the stats.

**Parameters**

* Index : int -Index of the player with the PreBakedActions in the Fight.PlayerList list.
* MainStat : int -Main stat's value.
* f_WD : float - Damage value attributed to the weapon. 
* f_DET : float - Damage value attributed to Determination.
* f_TEN : float - Damage value attributed to Tenacity.
* f_SPD : float - Damage value attributed to Spell Speed or Skill Speed.
* f_CritRate : float - Critical rate value.
* f_CritMult : float - Damange multiplier when a critical hit happens.
* f_DH : float - Direct Hit rate value.
* DHAuto : Direct Hit bonus to auto crit/DH.
* getInfo : bool - If set to true the function will return more information (DPS, TD, timeStamp, TP).

**Return**

This function returns the expected DPS and an empty dictionnary (float, dict). If getInfo is set to true
the function returns the expected DPS, the expected total damage, the end time stamp and the total potency (float, int, float, int).

.. note::
    f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto can be obtained by calling the function *computeDamageValue* located in *GearSolver.Solver*.

**Usage**

.. code-block:: python

    # Usage
    from ffxivcalc.GearSolver.Solver import computeDamageValue
    f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto = computeDamageValue(GearStat, JobMod, IsTank, IsCaster)
    ExpectedDamage, randomDamageDict, duration, potency = Fight.SimulatePreBakedFight(PlayerIndex, GearStat["MainStat"],f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto, n=n,getInfo = True)
