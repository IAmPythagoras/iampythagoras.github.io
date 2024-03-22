Gear.getMateriaTypeList()
=========================

This function returns a list of all different Materia's StatType currently on this gear.

**Parameter**

* IgnoreSpeedMateria : bool - If true the list ignores Speed related materias. (Default true)
* IgnorePietyMateria : bool - If true the list ignores Piety materias. (Default true)

**Return**

This function returns a list of stat type (list[StatType]).

**Usage**

.. code-block:: python

    newGear.getMateriaTypeList() # Ignores speed and piety
    newGear.getMateriaTypeList(IgnoreSpeedMateria=False,IgnorePietyMateria=False) # Ignores no materia