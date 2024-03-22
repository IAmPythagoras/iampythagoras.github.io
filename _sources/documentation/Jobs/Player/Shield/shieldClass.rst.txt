Shield
======

This class represents a shield. It will take damage before the main HP of a player
is reduced. A shield will remove itself if its time limit is reached.

**Class attributes**

* Shield.ShieldAmount : int - Current amount of HP the shield protects from.
* Shield.Timer : float - Current timer of the shield.
* Shield.Player : Player - Reference to the player that has this shield.
* Shield.ShieldName : str - Name of the shield.

**Class functions**

.. toctree::

    shieldInit
    shieldUpdateTimer