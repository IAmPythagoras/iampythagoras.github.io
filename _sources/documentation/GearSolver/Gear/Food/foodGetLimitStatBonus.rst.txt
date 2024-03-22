Food.getLimitStatBonus()
========================

This function returns the limit of the stat bonus for a given stat name.

**Parameter**

* StatName : str - Name of the stat.

**Return**

This function returns the value of the stat cap for that food (int). It returns 0 if the StatName is invalid.

**Usage**

.. code-block:: python

    HD = Food({"DH" : [103, 0.1], "Det" : [62, 0.1]}, "Honeyed Dragonfruit")

    HD.getLimitStatBonus("DH") # Returns 103
    HD.getLimitStatBonus("Crit") # Returns 0 since Crit is not a bonus of HD food.