ZipAction 
=========

This class is similar to a PreBakedAction but it contains more preprocessed information such.
In exchange it has less freedom when computing the damage from it. Because of that a ZIPAction is only used
to compute RandomDamage for generating DPS distribution graph.

**Class attributes**

* ZipAction.Damage : int - Value corresponding to the pre computed damage value of the action. Doesn't include DH, Crit damage or 95-105 range.
* ZipAction.CritChance : float - Critical chance of the action.
* ZipAction.CritMultiplier : float - Critical hit bonus on the action.
* ZipAction.DHChance : float - Direct hit chance of the action.
* ZipAction.auto_crit : bool - True if the action is an auto crit.
* ZipAction.auto_dh : bool - True if the action is an auto DH.
* ZipAction.AutoCritBonus : float - Damage bonus from crit buff when auto crit.
* ZipAction.AutoDHBonus : float - Damage bonus from direct hit when auto direct hit.

**Class functions**

.. toctree::

    zipActionInit
    zipActionComputeRandomDamage
