Enemy
=====

The *Enemy* object is one of the most important object of this library. It represents the boss of the simulation. This object keeps track of 
some raid wide effects like buff and mitigation.

**Class attributes**

* Enemy.EffectList : list[function] - List that contains all effects currently applied on this enemy.
* Enemy.TotalPotency : int - Total potency the enemy received.
* Enemy.TotalDamage : int - Total damage the enemy received.
* Enemy.buffList : list[function] - List of all buff a player receives when it attacks this enemy.
* Enemy.ChainStratagem : bool - If true the enemy has the chain stratagem buff on it.
* Enemy.WanderingMinuet : bool - If true the party has the buff wandering minuet applied to every actions.
* Enemy.BattleVoice : bool - If true the party has the buff battle voice applied to every actions.
* Enemy.ArmyPaeon : bool - If true the party has the buff army paeon applied to every actions.
* Enemy.Addle : bool - If true the enemy has addle applied to it.
* Enemy.Feint : bool - If true the enemy has feint applied to it.
* Enemy.Reprisal : bool - If true the enemy has reprisal applied to it.
* Enemy.EventList : list[EnemyEvent] - List of all EnemyEvent object this enemy will perform.
* Enemy.EventNumber : int - Index of the current event being performed.
* Enemy.hasEventList : bool - True if this enemy has a non-empty EventList.
* Enemy.CastingTimer : float - Current casting timer of this enemy.
* Enemy.AddleTimer : float - Current timer of addle on this enemy.
* Enemy.FeintTimer : float - Current timer of feint on this enemy.
* Enemy.ReprisalTimer : float - Current timer of reprisal on this enemy.
* Enemy.CastingAction : EnemyEvent - Currently casted EnemyEvent.
* Enemy.IsCasting : bool - True if the enemy is currently casting.
* Enemy.CurrentFight : Fight - Reference to the Fight object this enemy is part of.

**Class function**

.. toctree::
    enemyInnit
    enemySetEventList
    enemyUpdateTimer
