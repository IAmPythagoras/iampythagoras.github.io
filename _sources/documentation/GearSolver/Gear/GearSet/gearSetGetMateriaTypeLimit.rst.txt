GearSet.getMateriaTypeLimit()
=============================

This function returns the total amount of materia of the given StatType and even value MateriaGenerator that the gear set can receive.

**Parameters**

* type : StatType - Type of the materia to sum up.
* matGen : MateriaGenerator - MateriaGenerator that will be used to check if a materia can legally fit on each gear piece. It assumes even tier materia.

**Return**

This function returns the count of materias of the given StatType and even value that can fit onto the gear set (int).

**Usage**

.. code-block:: python

    newGearSet.getMateriaTypeLimit(StatType.Crit, MateriaGenerator(18,36))
    # This will return how many +36 Crit materias the gear set can receive.

    