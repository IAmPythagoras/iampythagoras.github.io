HealingBuff.UpdateTimer()
=========================

This function updates the HealingBuff's timer attribute. It also removes it from the player's healin buff list if the timer 
reaches 0.

**Parameter**

* time : float - Time to update the timer by (in seconds).

**Usage**

.. code-block:: python

    newHealingBuff.UpdateTimer(0.01)