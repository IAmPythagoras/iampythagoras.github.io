GearSet.removeMateriaType()
===========================

This function removes the first materia of the valid StatType found in every gear piece. It does that by calling Gear.removeMateriaType() on each Gear object in Gear.GearSet.

**Parameter**

* StatType : StatType - Type of the materia's stat to remove.

**Usage**

.. code-block:: python

    newGearSet.removeMateriaType(StatType.Crit) # Will attempt to remove
    # 1 Crit materia from every gear.

    