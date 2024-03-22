EnemyEvent.begin_cast()
=======================

This function will make a given enemy being the casting of the EnemyEvent event.

**Parameter**

* Enemy : Enemy - Enemy object that will perform the EnemyEvent event.

**Usage**

.. code-block:: python

    MagicRaidWide.being_cast(Enemy()) # The object Enemy() will start the cast of the MagicRaidWide EnemyEvent.

.. warning::

    Do not call this function. This function is automatically being called during the simulation.
