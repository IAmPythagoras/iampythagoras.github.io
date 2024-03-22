HealingBuff
===========

This class represents a healing buff given to a player. This object keeps track of the duration of the buff
and removes the buff once it is expired.

**Class attributes**

* HealingBuff.PercentBuff : float - Multiplicative value of the buff. If the buff is 20% then PercentBuff = 1.2
* HealingBuff.Timer : float - Timer of the buff.
* HealingBuff.Player : Player - Reference to the player object the buff is applied on.
* HealingBuff.GivenHealBuff : bool - If the buff only applies to heals that the player gives (and not receives).
* HealingBuff.BuffName : str - Name of the buff.

**Class functions**

.. toctree::

    healingBuffInnit
    healingBuffUpdateTimer