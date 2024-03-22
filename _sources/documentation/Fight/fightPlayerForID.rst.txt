Fight.playerForID()
===================

This function returns a reference to the player object that has the given ID in the fight. Raises *playerIDNotFound* if the given id is invalid.

**Parameters**

* id : int -Id of the requested player.

**Return**

This function returns a player object.

**Usage**

.. code-block:: python

    # Usage
    newFight.playerForID(1) # Retrieves the player object with ID 1
