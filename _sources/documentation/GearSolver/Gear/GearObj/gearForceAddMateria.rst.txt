Gear.forceAddMateria()
======================

This function does the same as Gear.AddMateria() but it will always allow the meld. It will set Gear.illegalMeld to true
if the resulting melding is illegal.

**Parameter**

* newMateria : Materia - Materia to add.

**Usage**

.. code-block:: python

    newGear.forceAddMateria(newMateria)