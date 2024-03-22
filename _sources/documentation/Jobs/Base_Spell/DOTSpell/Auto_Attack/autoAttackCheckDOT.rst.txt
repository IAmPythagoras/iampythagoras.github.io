Auto_Attack.CheckDOT()
======================

This serves the same purpose as DOTSpell.CheckDOT(), but it is a bit different as we have to check the player's auto delay when refreshing the DOT timer.

**Parameter**

* Player : Player - Player from which the DOT is coming from.
* Enemy : Enemy - Enemy on which the DOT is applied.
* TimeUnit : float - Time by which to update the DOT's timer.

**Usage**

.. code-block:: python

    newAA.CheckDOT(newPlayer, newEnemy, 0.01)