Fight.GetEnemityList()
======================

Returns a list of players in order of greather enemity to lowest enemity. The length of the returned list is equal to the value of *range*.

**Parameters**

* range : int -Length of the returned list.

**Return**

This function returns a list of player objects.

**Usage**

.. code-block:: python

    # Usage
    list = newFight.GetEnemityList(2) # This would return the 2 players with the most enemity.
