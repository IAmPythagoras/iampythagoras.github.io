GearType.name_for_id()
========================

This function returns the name of the gear type given an id. This function is a classmethod and so it must
be called on the class of GearType itself.

**Parameter**

* id : int - Id of the gear type.

**Return**

This function returns a string. It either returns the name of the gear type (if it was found)
or returns 'INVALID' if it didn't find it.

**Usage**

.. code-block:: python

    GearType.name_for_id(0) # Returns WEAPON
    GearType.name_for_id(10) # Returns LRIGN
    GearType.name_for_id(13) # Returns INVALID
