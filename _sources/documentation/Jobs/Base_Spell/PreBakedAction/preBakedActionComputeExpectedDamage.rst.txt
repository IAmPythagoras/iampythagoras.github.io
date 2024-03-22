PreBakedAction.ComputeExpectedDamage()
======================================

This function computes the expected damage dealt by a PreBakedAction given damage parameters as input.

**Parameters**

* f_MAIN_DMG : float - Damage parameter due to main stat.
* f_WD : float 
* f_WD : float - Damage value attributed to the weapon. 
* f_DET : float - Damage value attributed to Determination.
* f_TEN : float - Damage value attributed to Tenacity.
* f_SPD : float - Damage value attributed to Spell Speed or Skill Speed.
* f_CritRate : float - Critical rate value.
* f_CritMult : float - Damange multiplier when a critical hit happens.
* f_DH : float - Direct Hit rate value.
* DHAuto : float - Multiplicative buff from DH when auto DH happens.

**Return**

This function returns the Expected damage value and the damage value before any random elements are applied (ie: crit and DH damage expected). the 'Damage' value can be then used to compute
random damage using the PreBakedAction.ComputeRandomDamage() function. Returns (ExpectedDamage, Damage).

**Usage**

.. code-block:: python

    f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto = computeDamageValue(GearStat, JobMod, IsTank, IsCaster)
    f_MAIN_DMG = 1.2 # Would need to compute this actual value.
    expectedDamage, nonCritnonDHDamage = newPreBakedAction.ComputeExpectedDamage(f_MAIN_DMG,f_WD, f_DET, f_TEN, f_SPD, f_CritRate, f_CritMult, f_DH, DHAuto)