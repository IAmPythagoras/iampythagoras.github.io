Gear.AddMateria()
=================

This function adds a Materia object to the gear. This function also flags the materia is any stat is wasted.

**Parameter**

* newMateria : Materia - Materia to add.

.. warning::

    This function raises *MateriaOverflow* if the gear piece has reached its materia limit.

**Usage**

.. code-block:: python

    newGear.AddMateria(newMateria)

