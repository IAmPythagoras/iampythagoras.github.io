Spell
=====

This class represents any action that can be done by a player.


**Class attributes**

* Spell.id : int - Unique identifier of the action.
* Spell.GCD : bool - True if the action is a GCD.
* Spell.Potency : int - Potency of the action.
* Spell.ManaCost : int - Mana cost of the action.
* Spell.CastTime : float - Base casting time of the action.
* Spell.RecastTime : float - Base recast time of the action. Only GCD should have non zero recast time. This determines for how long the player is locked.
* Spell.Effect : list[function] - List of all functions to apply once the action is casted.
* Spell.Requirement : function - Function that checks if the action can be performed.
* Spell.DPSBonus : float - Multiplicative bonus on damage.
* Spell.TargetID : int - Id of the target. 0 Means an enemy is being targetted and non zero ID is another player.
* Spell.TargetPlayerObject : Player - Player object of the player target (if it applies).
* Spell.type : int - Type of the action (0 = Ability, 1 = Spell, 2 = Weaponskill and 3 = Limit Break).
* Spell.AOEHeal : bool - True if the action is classfied as an AOE heal (ex: succor).
* Spell.TargetHeal : bool - True if the action has a healing target (ex: addloquium).
* Spell.conditionalAction : bool - True if the action is a conditional action.

**Class functions**

.. toctree::

    spellInit
    spellCast
    spellCastFinal

Most actions done by players are subclass of Spell. For example, actions done by a blackmage are of the class *BLMSpell*.

**Subclass**

.. toctree::

    DOTSpell/dotSpellClass