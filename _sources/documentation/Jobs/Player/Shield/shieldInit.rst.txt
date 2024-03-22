Shield.__init__()
=================

This is the constructor of the shield class.

**Parameters**

* ShieldAmount : int - Current amount of HP the shield protects from.
* Timer : float - Current timer of the shield.
* Player : Player - Reference to the player that has this shield.
* ShieldName : str - Name of the shield.

**Usage**

.. code-block:: python

    newShield = HealingBuff(1.2, 30, Player(), BuffName="Dissipation")