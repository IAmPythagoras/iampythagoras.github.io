HealingBuff.__init__()
======================

This is the constructor of the class HealingBuff.

**Parameters**

* PercentBuff : float - Multiplicative value of the buff. If the buff is 20% then PercentBuff = 1.2
* Timer : float - Timer of the buff.
* Player : Player - Reference to the player object the buff is applied on.
* GivenHealBuff : bool - If the buff only applies to heals that the player gives (and not receives).
* BuffName : str - Name of the buff.

**Usage**

.. code-block:: python

    newHealingBuff = HealingBuff(1.2, 10, Player(), True, "GiveHeal")