Gear.GetStat()
==============

This function returns the Stat.Value of the Stat object requested.

**Parameters**

* StatName : str - Name of the stat to get. (Default "")
* StatEnum : StatType - StatType of the stat to get. (Default -2)

.. note::

    You only have to use one of StatName or StatEnum. If both are given the value for StatEnum will be taken.

.. warning::

    If this function is called with default values for both StatName and StatEnum it will raise an *InvalidStatRequest* error.

**Return**

This function returns the value of the requested stat (int). It returns 0 if the stat is not on this gear piece.

**Usage**

.. code-block:: python

    newGear.GetStat(StatName = "Det")# Would get Det
    newGear.GetStat(StatEnum=StatType.Crit) # Would get Crit
    newGear.GetStat(StatName="Det", StatEnum=StatType.Crit) # Would get Crit

    newGear.GetStat() # Invalid and raised error.
