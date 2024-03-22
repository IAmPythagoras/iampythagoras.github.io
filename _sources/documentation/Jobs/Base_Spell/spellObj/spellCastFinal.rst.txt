Spell.CastFinal()
=================

This function is used to apply an action once its casting is done. This function applies any effect the action might have, requests to compute the damage of the action and updates any
relevant counter attributes.

**Parameters**

* player : Player - Player object casting the action.
* Enemy : Enemy - Enemy object being the target of the action (This is still non null even if the action does not do anything to the enemy).

**Usage**

.. code-block:: python
    
    player = Player()
    Enemy = Enemy()
    currentSpell = newSpell.Cast(player,Enemy )
    currentSpell.CastFinal(player, Enemy)