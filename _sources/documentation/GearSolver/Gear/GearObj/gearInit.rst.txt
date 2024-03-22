Gear.__init__()
===============

This is the constructor of the Gear object.

**Parameters**

* GearType : GearType - Type of the gear.
* StatList : List[Stat] - List of Stat object. Stats of the gear piece.
* MateriaLimit : int - Limit of materia the gear can receive (default 2).
* Name : str - Name of the gear (Default is nothing "").

**Usage**

.. code-block:: python

    newGear = Gear(GearType.WEAPON, [Stat1, Stat2, Stat3], MateriaLimit = 3, Name="Ultimate weapon")
    