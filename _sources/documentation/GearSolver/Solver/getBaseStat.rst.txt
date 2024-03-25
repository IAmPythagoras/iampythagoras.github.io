getBaseStat()
=============

This function returns a dictionnary that corresponds to the base stats of a player.

**Parameter**

* IsTank : bool - True if the player is a tank (Default false). A tank has lower base value for MainStat.

**Return**

This function returns a stat dictionnary that can be given to a Player object (dict[str : int]).

**Usage**

.. code-block:: python

    baseStat = getBaseStat(IsTank=True)
