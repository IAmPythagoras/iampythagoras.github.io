StatType.name_for_id()
========================

This function returns the name of the stat type given an id. This function is a classmethod and so it must
be called on the class of StatType itself.

**Parameter**

* id : int - Id of the stat type.

**Return**

This function returns a string. It either returns the name of the stat type (if it was found)
or returns 'Unknown' if it didn't find it.

**Usage**

.. code-block:: python

    StatType.name_for_id(0) # Returns Crit
    StatType.name_for_id(8) # Returns WD
    StatType.name_for_id(13) # Returns Unknown