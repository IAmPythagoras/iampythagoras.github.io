EnemyEvent.cast()
=================

This function applies the effect of the EnemyEvent. Automatically called when the EnemyEvent is done being casted.

**Parameters**

* Enemy : Enemy - Object of the Enemy casting the event.

**Usage**

.. code-block:: python

    MagicRaidWide.cast(Enemy()) # Enemy() object will cast MagicRaidWide.

.. warning::

    Do not call this function. This function is automatically being called during the simulation.

