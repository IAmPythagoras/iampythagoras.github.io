Player.updateTimer()
====================

This function updates all relevant base timer of the player. It also calls the *updateTimer()* function specific to the player's role and job.

**Parameter**

* time : float - Time by which to update the timers by (in seconds).

**Usage**

.. code-block:: python

    Player().updateTimer(0.01) # Update the timers by 0.01 seconds.

.. warning::

    Do not call this functions. It is being automatically called during simulation.