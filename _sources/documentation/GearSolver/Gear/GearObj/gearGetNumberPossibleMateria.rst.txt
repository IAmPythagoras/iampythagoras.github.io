Gear.getNumberPossibleMateria()
===============================

This function returns the total number of materia that can be added to the gear with no loss of the given stat type.

.. warning::

    For now this function assumes we are using even tier materias.

**Parameters**

* type : StatType - Type of the stat to check.
* matGen : MateriaGenerator - MateriaGenerator object for which we want to check how many materias can fit.

**Return**

This function returns the amount of the given materia type that can legally fit onto the object (int).

**Usage**

.. code-block:: python

    newGear.getNumberPossibleMateria(StatType.Crit, MateriaGenerator(18,36))
    # This would check how many materias of +36 Crit can fit in the newGear object.

