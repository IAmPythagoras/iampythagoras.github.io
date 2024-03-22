EnemyEvent
==========

This class represents an action or event an Enemy object can do. Such events can be raidwide, a mechanic, untargetable, an enrage, etc.

**Class attributes**

* EnemyEvent.CastTime : float - CastTime of the event in seconds.
* EnemyEvent.id : int - Unique identifier of the event.
* EnemyEvent.Damage : int - Amount of damage dealt to the players.
* EnemyEvent.RaidWide : bool - True if the event applies raid wide damage.
* EnemyEvent.nTBTarget : int - Number of target the event has. Assumed to be a tank buster.
* EnemyEvent.IsPhysical : bool - True if the event applies physical damage.
* EnemyEvent.target : list[Player] - List of Player object targetted by the event.


**Class functions**

.. toctree::
    enemyEventInnit
    enemyEventBeginCast
    enemyEventCast