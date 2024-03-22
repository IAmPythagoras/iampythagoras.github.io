Materia.__str__()
=================

This is the function that casts a materia object into a string.

**Return**

This function returns a string of the format : 'Materia.StatName : Materia.Value'.

**Usage**

.. code-block:: python

    newMateria = Materia(StatType.Det, 36)
    print(newMateria)
    # Det : 36