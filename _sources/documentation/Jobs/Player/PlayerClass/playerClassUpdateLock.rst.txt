Player.updateLock()
===================

This function updates the value of the timer for GCDLock, oGCDLock and CastingLock of the player. If it detects that the player is done casting it will
also call the function to cast the action.

.. note::

    This function takes no input and updates by using the Player.CurrentFight.TimeUnit value

**Usage**

.. code-block:: python

    Player.updateLock()

.. warning::

    Do not call this functions. It is being automatically called during simulation.