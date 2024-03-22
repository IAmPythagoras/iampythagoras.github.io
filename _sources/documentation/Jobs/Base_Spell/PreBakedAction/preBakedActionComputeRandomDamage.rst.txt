PreBakedAction.ComputeRandomDamage()
====================================

This function computes the random damage done by a PreBakedAction. This function is designed to be called after using PreBakedAction.ComputeExpectedDamage()
and using the 2nd return of that function to pass as argument to this function.

**Parameters**

* Damage : int - Damage value of the action without any random element to it. This corresponds to the base damage with buffs applied and no crit or dh buff.
* f_CritRate : float - Critical hit rate of the action.
* f_CritMult : float - Damange multiplier when a critical hit happens.
* f_DH : float - Direct hit rate of the action.

**Returns**

This function returns the random damage (int).

**Usage**

.. code-block:: python

    f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto = computeDamageValue(GearStat, JobMod, IsTank, IsCaster)
    f_MAIN_DMG = 1.2 # Would need to compute this actual value.
    expectedDamage, nonCritnonDHDamage = newPreBakedAction.ComputeExpectedDamage(f_MAIN_DMG,f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto)

    # Using PreBakedAction.ComputeExpectedDamage() to get required damage value.

    randomDamage = newPreBakedAction.ComputeRandomDamage(nonCritnonDHDamage, f_CritRate, f_CritMult, f_DH)

.. warning::

    This function will not work if PreBakedAction.ComputeExpectedDamage() is not called before as some values needed in PreBakedAction.ComputeRandomDamage() are initialized and computed in PreBakedAction.ComputeExpectedDamage()