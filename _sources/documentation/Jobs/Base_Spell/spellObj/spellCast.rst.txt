Spell.Cast()
============

This is the function responsible for starting the cast of any action. Any subclass of Spell uses this function when being casted. This function
is responsible for applying any effects to the action (ex : lowering cast time), for checking all requirements and letting the simulation know if a fatal error happened and it also
locks the player into a *casting* state by modifying the required player attributes.

**Parameters**

* player : Player - Player object casting the action.
* Enemy : Enemy - Enemy object being the target of the action (This is still non null even if the action does not do anything to the enemy).

**Return**

This function returns a Spell object. In more details, this function alters the given spell object. So to not create any issues a deepcopy of the original
Spell object is created and returned in this function. Any subsequent call or use must be done on this returned object.

**Usage**

.. code-block:: python

    currentSpell = newSpell.Cast(Player(), Enemy())

