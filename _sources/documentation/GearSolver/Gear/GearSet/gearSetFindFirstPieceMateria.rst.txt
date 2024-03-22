GearSet.findFirstPieceMateria()
===============================

This function returns the key to the first piece of gear in the gear set that can have the newMateria attached to it without loss. If none is found, the function returns None.

**Parameter**

* newMateria : Materia - Materia to look for a slot.

**Return**

This function returns the key of the Gear that can receive the Materia without loss (str) or None if no Gear can receive the materia without loss.

**Usage**

.. code-block:: python

    potentialGearName = newGearSet.findFirstPieceMateria(newMateria)