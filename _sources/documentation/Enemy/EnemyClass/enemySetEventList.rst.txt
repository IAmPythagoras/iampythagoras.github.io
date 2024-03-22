Enemy.setEventList()
====================

This function sets the EventList of the Enemy object. 

**Parameter**

* newEventList : list[EnemyEvent] - List of EnemyEvent object.

**Error**

This function will raise *emptyEventList* if the given newEventList is empty.

**Usage**

.. code-block:: python

    newEnemy.setEventList([WaitEvent(2)]) # Will append an EnemyEvent that makes the enemy wait for 2 seconds.