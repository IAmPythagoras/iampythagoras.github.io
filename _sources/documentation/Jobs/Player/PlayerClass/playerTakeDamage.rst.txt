Player.TakeDamage()
===================

Updates the value of the player's HP given some damage. Sets the player in a death state if the player's death is detected (reaches 0) (does that by setting Player.TrueLock = True).

**Parameters**

* DamageAmount : int - Damage taken.
* MagicDamage : bool - True if the damage taken is magical. False if it is physical.

**Usage**

.. code-block:: python 

    newPlayer.TakeDamage(12000)