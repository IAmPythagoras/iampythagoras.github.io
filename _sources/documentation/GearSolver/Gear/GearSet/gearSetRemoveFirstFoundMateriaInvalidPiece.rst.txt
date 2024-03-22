GearSet.removeFirstFoundMateriaInvalidPiece()
=============================================

This function removes the first found materia of the given type on an illegal gear piece. If none is found the function returns None and otherwise it returns the name of the gear piece from which a materia was removed.

This function only removes 1 materia and does not remove 1 from every gear. 

**Parameter**

* StatType : StatType - Type of the materia to remove.

**Return**

This function returns the name of the gear from which the materia was removed (str). It returns None if no gear piece fit the requirement.

**Usage**

.. code-block:: python

    newGearSet.removeFirstFoundMateriaInvalidPiece(StatType.Crit)