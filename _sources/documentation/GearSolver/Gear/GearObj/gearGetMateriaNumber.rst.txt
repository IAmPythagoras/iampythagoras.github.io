Gear.getMateriaNumber()
=======================

This function returns the number of materia of each StatTypes currently on this gear piece.

**Parameter**

* dictData : dict[str : int] - This maps the name of a stat to its materia count. During the execution of the function it will be filled with the count of each different materias.

**Return**

This function modifies the given dictData.

**Usage**

.. code-block:: python

    newDict = {}
    newGear.getMateriaNumber(newDict)
    newGear2.getMateriaNumber(newDict)
    # newDict now contains the count of each materia for both newGear and newGear2.

    