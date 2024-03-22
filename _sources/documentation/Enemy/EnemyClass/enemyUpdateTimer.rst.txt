Enemy.UpdateTimer()
===================

.. warning::

    This function should not be called. It is being used by the simulator to update different
    timer.

This function updates the different timer of the Enemy object.
This function also casts an EnemyEvent if the value of Enemy.CastingTimer reaches 0.

**Parameter**

* time : float - Length of temporal update in seconds.

**Usage**

.. code-block:: python

    newEnemy.UpdateTimer(0.01) # Updates the different timer by 0.01 seconds.