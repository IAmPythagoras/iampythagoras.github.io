Food.getPercentStatBonus()
==========================

This function returns the percent bonus of a given StatType for the food.

**Parameter**

* StatName : str - Name of the stat.

**Return**

This function returns a floating point value corresponding to the percent buff of the stat. It returns 0 if the stat is invalid.

**Usage**

.. code-block:: python

        HD = Food({"DH" : [103, 0.1], "Det" : [62, 0.1]}, "Honeyed Dragonfruit")

    HD.getLimitStatBonus("DH") # Returns 0.1
    HD.getLimitStatBonus("Crit") # Returns 0 since Crit is not a bonus of HD food.