Player.AddMitBuff()
===================

Appends a MitBuff object to the player's MitBuffList. If the mit is non-stackable it resets the timer of the already present buff if already present and does not append.

**Parameter**

* buff : MitBuff - MitBuff object to append.
* stackable : bool - If true the buff can stack (default false).

**Usage**

.. code-block:: python

    newPlayer.AddMitBuff(newMitBuff)

    