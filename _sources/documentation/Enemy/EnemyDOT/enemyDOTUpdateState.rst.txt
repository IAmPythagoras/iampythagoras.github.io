EnemyDOT.updateState()
======================

This function updates the internal value of the EnemyDOT object such as EnemyDOT.DOTDuration and EnemyDOT.DOTStateTimer.
This function also applies damage if the tic timer reaches 0.

**Parameter**

* time : float - Amount of time to update by.
* player : Player - Player object on which the DOT is currently applied.

**Usage**

.. code-block:: python

    newEnemyDOT.updateState(0.01, Player()) # This is not a correct constructor of the Player object.

.. warning::

    Do not call this function as it is being automatically used during simulation.