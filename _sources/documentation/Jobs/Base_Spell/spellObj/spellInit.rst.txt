Spell.__init__()
================


This is the constructor of the class 

**Parameters**

* id : int - Unique identifier of the action.
* GCD : bool - True if the action is a GCD.
* Potency : int - Potency of the action.
* ManaCost : int - Mana cost of the action.
* CastTime : float - Base casting time of the action.
* RecastTime : float - Base recast time of the action. Only GCD should have non zero recast time. This determines for how long the player is locked.
* Effect : function - Function to be applied once the action is casted.
* Requirement : list[function] - List of functions that checks if the action can be performed. All of the function must return True for the action to be legal.
* DPSBonus : float - Multiplicative bonus on damage.
* TargetID : int - Id of the target. 0 Means an enemy is being targetted and non zero ID is another player.
* TargetPlayerObject : Player - Player object of the player target (if it applies).
* type : int - Type of the action (0 = Ability, 1 = Spell, 2 = Weaponskill and 3 = Limit Break).
* AOEHeal : bool - True if the action is classfied as an AOE heal (ex: succor). (Default : False)
* TargetHeal : bool - True if the action has a healing target (ex: addloquium). (Default : False)

**Usage**

.. code-block:: python

    def applySpell(Player, Enemy):
        Player.HP += 10

    def spellRequirement(Player, Spell):
        return Player.HP < 100, -1

    newSpell = Spell(1, True, 2.5, 2.5, 100, 200, applySpell, [spellRequirement], type=1)

**Creating job and class specific actions**

In practice most actions are not a Spell and are a class derived from it. For example, the class *BLMSpell* represents an action that can be performed by a blackmage and *BLMSpell* is a subclass
of Spell. There is one such class for each job and for each role. To import all actions that a player can perform, use the following import structure :

.. code-block:: python

    from ffxivcalc.Jobs.__ROLE__.__JOB__.__JOB___Spell import *
    from ffxivcalc.Jobs.Caster.Blackmage.BlackMage_Spell import * # Import all BlackMage actions
    from ffxivcalc.Jobs.Caster.Caster_Spell import * # Import all actions that any caster can perform.

    from ffxivcalc.Jobs.Healer.Healer_Spell import * # Import all actions that any healer can perform
    from ffxivcalc.Jobs.Healer.Scholar.Scholar_Spell import * # Import all Scholar actions.

Every subclass of Spell has their own constructor that might differ in need. Refer to the different files on the github repository for more information.
