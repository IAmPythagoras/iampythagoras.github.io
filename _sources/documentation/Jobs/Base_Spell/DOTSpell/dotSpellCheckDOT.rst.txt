DOTSpell.CheckDOT()
===================

This function updates the DOT's internal timer (DOTSpell.DOTTimer) and applies damage if this timer is equal to 0 (and then restart the timer).
This function is automatically called during the simulation's execution.

**Parameter**

* Player : Player - Player from which the DOT is coming from.
* Enemy : Enemy - Enemy on which the DOT is applied.
* TimeUnit : float - Time by which to update the DOT's timer.

**Usage**

.. code-block:: python

    newDOT.CheckDOT(newPlayer, newEnemy, 0.01)