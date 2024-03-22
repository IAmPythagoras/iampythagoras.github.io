Food
====

Food is a class that represents any food that a player can eat to increase its stat.

**Class attributes**

* Food.name : str - Name of the food.
* Food.statBonusDict : dict[str : (int, float)] - Dictionnary that contains information about the food's buff. The key is the name of the StatType and it maps to a tuple that contains the buff cap and the percentage buff.


**Class functions**

.. toctree::

    foodInit
    foodGetLimitStatBonus
    foodGetPercentStatBonus
    foodStr
