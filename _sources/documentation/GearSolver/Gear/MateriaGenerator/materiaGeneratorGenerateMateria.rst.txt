MateriaGenerator.GenerateMateria()
==================================

This function generates a materia out of the MateriaGenerator object.

**Parameters**

* StatType : StatType - Type of the stat of the generated materia.
* Even : bool - If true the created materia is even tier and uses the MateriaGenerator.EvenValue as its value (default True).

**Return**

This function returns a Materia object corresponding to the required generation.

**Usage**

.. code-block:: python

    newMatGen = MateriaGenerator(18, 36) 

    newMatGen.GenerateMateria(StatType.Crit) # Generate a +36 crit materia
    newMatGen.GenerateMateria(StatType.Det) # Generate a +36 Det materia
    newMatGen.GenerateMateria(StatType.Det, Even=False) # Generate a +18 Det materia