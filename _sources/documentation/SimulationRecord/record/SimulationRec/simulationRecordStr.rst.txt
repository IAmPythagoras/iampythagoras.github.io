SimulationRecord.__str__()
==========================

Casts the simulation record as a string. The returned string will limit to the pages that match the player ids in SimulationRecord.idList if it is not empty.

**Return**

This function returns a string that prints out every page of the record (using page.__str__()).

**Usage**

.. code-block:: python

    print(str(newSimRec))
