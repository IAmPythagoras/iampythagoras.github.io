ComputeDamage()
===============

.. note::
    This function is not part of the class *Fight*.

This function returns the expected damage of an action.

**Parameter**
* Player : player - Reference to the Player object doing the damage.
* Potency : int - Potency of the action.
* Enemy : Enemy - Enemy object taking the damage
* SpellBonus : float - Multiplicative damage buff applied on this action.
* type : int - Type of the action. 0 is Direct Damage, 1 is magical DOT, 2 is physical DOT,  3 is autos
* spellObj : Spell - Object of the spell being casted
* SavePreBakedAction : bool - If set to true the function will record the action to the player's PreBakedAction list (if it matches id). False by default.
* PlayerIDSavePreBakedAction : int - ID of the player for which we want to record the PreBakedActions.

**Return**

This function returns a tuple of 0, ExpectedDamage (int, int).

**Usage**

.. code-block:: python
    
    from ffxivcalc.Fight import ComputeDamage
    x, expectedDamage = ComputeDamage(Player(), 100, Enemy(), 1.00, 2, Spell(), False, 0)
