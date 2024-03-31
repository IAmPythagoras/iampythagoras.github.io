Player.AddHealingBuff()
=======================

Appends a HealingBuff object to the player's ReceivedHealBuffList or GivenHealBuffList. If an identical non-stackable effect is found it resets the timer of that buff and does not append.

**Parameters**

* buff : HealingBuff - HealingBuff object to append.
* GivenHealBuff : bool - If true the HealingBuff is applied on healing given by this player, if False it is applied on the received heals (Default True).
* stackable : bool - True if the buff can stack multiple times (default false).

**Usage**

.. code-block:: python 

    newPlayer.AddHealingBuff(newHealingBuff)