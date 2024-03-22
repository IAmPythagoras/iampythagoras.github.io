GearSet.__next__()
==================

This is the next(GearSet) implementation. It updates the iter object held in GearSet.gearSetIter and returns
the next Gear object.

**Return**

This function returns the next Gear object in line.

**Usage**

.. code-block:: python

    next(newGearset)

    for gear in GearSet:
        gear.DoSomething()