Gear.__hasStatType()
====================

.. note::

    This is a private function that can only be called within the Gear class.

This function returns weither the given StatType has non zero value for this gear.

**Parameter**

* type : StatType - Type of the stat to check.

**Return**

This returns true if the stat has a non zero value (boolean).

**Usage**

.. code-block:: python

    newGear.__hasStatType(StatType.Crit)