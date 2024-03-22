Gear.removeMateriaType()
========================

This function removes the first materia of the given StatType found on the gear. This function updates the value of Gear.illegalMeld if the gear is now valid after removing the materia.

If no materia of the given StatType is found no error is raised.

**Parameter**

* statType : StatType - Type of stat to remove.

**Usage**

.. code-block:: python

    newGear.removeMateriaType(StatType.Crit)