getGearDPSValue()
=================

This function returns the expected dps of the given gear set and fight (for one player).

**Parameters**

* Fight : Fight - Fight object. 
* gearSet : GearSet - This gear set will be given to the player of choice.
* PlayerIndex : int - Index in the Fight.PlayerList of the player to test the gear set with.
* PlayerID : int - ID of the player object to test the gear set with.

**Return**

This function returns a tuple of (ExpectedDamage, randomDamageDict) (int, dict[str : int]). It also prints the result to the terminal.

**Usage**

.. code-block:: python

    getGearDPSValue(Fight(), GearSet(), 0, 1)