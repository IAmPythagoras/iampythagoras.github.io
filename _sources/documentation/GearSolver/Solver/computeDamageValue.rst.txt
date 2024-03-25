computeDamageValue()
====================

Computes and returns all the damage functions (f_WD, f_DET, etc.)given a stat dictionnary. This function does NOT compute f_MAIN_DAMAGE.

**Parameters**

* GearStat : dict[str : int] - Stats dictionnary to compute the damage functions of.
* JobMod : int - JobMod to compute the damage functions with
* IsTank : bool - If the player is a tank.
* IsCaster : bool - If the player is a caster (if they use Spell Speed).

**Returns**

This function returns a tuple corresponding to (f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto) where all those values are floats.

**Usage**

.. code-block:: python
    
    # Example stat dict
    statDict = {
        "MainStat" : 1000,
        "WD" : 100,
        "Det" : 1000,
        "Ten" : 400,
        "SS" : 800,
        "SkS" : 400,
        "Crit" : 2000,
        "DH" : 1400,
        "Piety" : 390
    }  

    f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto = computeDamageValue(statDict, 110, False, True)