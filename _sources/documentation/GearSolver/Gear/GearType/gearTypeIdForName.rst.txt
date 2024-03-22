GearType.id_for_name()
========================

This function returns the id of a gear type given a name. This function is a classmethod and so it must
be called on the class of GearType itself.

**Parameter**

* name: str - Name of the gear type.

**Return**

This function returns the id of the gear type (int) if it was found. It returns (-1) if it was not found.

**Usage**

.. code-block:: python

    GearType.id_for_name("WEAPON") # Returns 0
    GearType.id_for_name("LRING") # Returns 10
    GearType.id_for_name("BOOT") # Returns -1