StatType.id_for_name()
========================

This function returns the id of a stat type given a name. This function is a classmethod and so it must
be called on the class of StatType itself.

**Parameter**

* name: str - Name of the stat type.

**Return**

This function returns the id of the stat type (int) if it was found. It returns (-1) if it was not found.

**Usage**

.. code-block:: python

    StatType.id_for_name("Crit") # Returns 0
    StatType.id_for_name("MainStat") # Returns 7
    StatType.id_for_name("SpellSpeed") # Returns -1