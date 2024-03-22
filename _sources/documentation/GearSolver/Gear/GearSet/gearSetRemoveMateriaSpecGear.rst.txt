GearSet.removeMateriaSpecGear()
===============================

This function removes the first materia of the given type from the given gear name.

**Parameter**

* gearName : str - Name of the gear's type to remove a materia from.
* type : StatType - Stat of the materia's stat to attempt to remove.

**Usage**

.. code-block:: python

    newGearSet.removeMateriaSpecGear("WEAPON", StatType.Crit) # Attemps to remove a Crit materia from the WEAPON.
    