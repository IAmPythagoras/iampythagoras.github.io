Fight.syncPlayerPrePull()
=========================

Computes the required time to be added to every player's ActionSet so all player start doing damage at the same time.

**Parameter**

* editActionSet : bool - If set to true this function will insert the required WaitAbility() action to every player's ActionSet (default true).

**Return**

Returns a dictionnary where the key is a player's id (int) and it maps to the required added time so all players start at the same time (float).

**Usage**

.. code-block:: python 

    newFight.syncPlayerPrePull()