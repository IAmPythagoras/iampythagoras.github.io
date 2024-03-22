ZipAction.__init__()
====================

This is the constructor of the ZipAction class.

**Parameters**

* Damage : int - Value corresponding to the pre computed damage value of the action. Doesn't include DH, Crit damage or 95-105 range.
* CritChance : float - Critical chance of the action.
* CritMultiplier : float - Critical hit bonus on the action.
* DHChance : float - Direct hit chance of the action.
* auto_crit : bool - True if the action is an auto crit. (Default False)
* auto_dh : bool - True if the action is an auto DH. (Default False)
* AutoCritBonus : float - Damage bonus from crit buff when auto crit. (Default 1)
* AutoDHBonus : float - Damage bonus from direct hit when auto direct hit. (Default 1)

**Usage**

.. code-block:: python

    newZipAction = ZipAction(1000, 1.2, 1.6, 1.2, auto_crit=True, auto_dh=False,AutoCritBonus=1, AutoDHBonus=1)