MitBuff
=======

This class represents a mitigation buff given to a player. This object keeps track of the duration of the buff
and removes the buff once it is expired.

**Class attributes**

* MitBuff.PercentMit : float -Percentage of the original damage taken once mitigation is applied. So if 30% mit, PercentMit = 0.7.
* MitBuff.Timer : float - Timer of the mit.
* MitBuff.Player : Player - Reference to the player on which this MitBuff is applied.
* MitBuff.MagicMit : bool - If the mitigation applies ONLY to magic damage.
* MitBuff.PhysicalMit : bool - If the mitigation applies ONLY to physical damage.
* MitBuff.TrueMit : bool - If the mitigation applies to both magical and physical damage.
* MitBuff.BuffName : str - Name of the MitBuff.

**Class functions**

.. toctree::

    mitBuffInnit
    mitBuffUpdateTimer