GearSet.getMateriaTypeList()
============================

This function returns a list of type of the materias present in the gear set.

**Parameter**

* IgnoreSpeedMateria : bool - If true the function will only return non Speed related stattype. Default True.
* IgnorePietyMateria : bool - If true this function ignores Piety Materia. Default True.
* ignoreValidMeld : bool - If true, function only returns materias type that are on at least one gear with invalidMelding. Default False.

**Return**

This function returns a list of all stat type (list[StatType]) that fit the search requirement.

**Usage**

.. code-block:: python

    newGearSet.getMateriaTypeList()
    newGearSet.getMateriaTypeList(IgnoreSpeedMateria=False, IgnorePietyMateria=False, ignoreValidMeld=True)