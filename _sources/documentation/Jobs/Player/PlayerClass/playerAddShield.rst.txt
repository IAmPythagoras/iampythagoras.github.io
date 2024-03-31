Player.AddShield()
==================

Appends a Shield object to the player's ShieldList. If the shield is non-stackable then it will only reset the timer of the already applied shield and won't append.

**Parameter**

* shield : Shield - Shield object to append.
* stackable : bool - If true the shield can stack (default false).

**Usage**

.. code-block:: python 

    newPlayer.AddShield(newShield)