GearSet.GetGearSetStat()
========================

This function returns a dictionnary that shows the different stats of the gear set.

**Parameter**

* IsTank : bool - Set to true if this gear set will be put on a tank. (Default False)

**Return**

Returns a dictionnary [str : int] where the key is the name of the stat and it maps to the value of this stat of the gear set.

**Usage**

.. code-block:: python

    newGearSet.GetGearSetStat()
    # {'MainStat': 3378, 'WD': 132, 'Det': 1530, 'Ten': 400, 'SS': 2521, 'SkS': 400, 'Crit': 851, 'DH': 1331, 'Piety': 390}

    newGearSet.GetGearSetStat(IsTank=True)
    # {'MainStat': 3378, 'WD': 132, 'Det': 1666, 'Ten': 400, 'SS': 400, 'SkS': 714, 'Crit': 2595, 'DH': 1258, 'Piety': 390}
