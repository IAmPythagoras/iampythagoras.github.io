Food.__init__()
===============

This function is the constructor of the class Food.

**Parameters**

* statBonusDict : dict[str : (int, float)] - Dictionnary that contains information about the food's buff. The key is the name of the StatType and it maps to a tuple that contains the buff cap and the percentage buff.
* name : str - Name of the food.

**Usage**

.. code-block:: python

    HD = Food({"DH" : [103, 0.1], "Det" : [62, 0.1]}, "Honeyed Dragonfruit")
    DB = Food({"SkS" : [103, 0.1], "DH" : [62, 0.1]}, "Dragonfruit Blend")
    BG = Food({"Crit" : [103, 0.1], "SkS" : [62, 0.1]}, "Baba Ghanoush")
    BE = Food({"Det" : [103, 0.1], "Crit" : [62, 0.1]}, "Baked Eggplant")
    CW = Food({"SS" : [103, 0.1], "DH" : [62, 0.1]}, "Caviar Sandwich")
    CC = Food({"Crit" : [103, 0.1], "SS" : [62, 0.1]}, "Caviar Canapes")
    MB = Food({"Ten" : [103, 0.1], "Det" : [62, 0.1]}, "Marinated Broccoflower")
    BS =  Food({"Det" : [103, 0.1], "Ten" : [62, 0.1]}, "Broccoflower Stew")