EnemyEvent.__init__()
=====================

This is the constructor of the class EnemyEvent.

**Parameters**

* id : int - Unique id of the event.
* CastTime : float - Casting time of the event in seconds.
* Damage : int - Damage of the event.
* RaidWide : bool - If is a raidwide.
* nTBTarget : int - Number of target for the event. Assumed to be a tank buster.
* IsPhysical : bool - If deals physical damage.
* Experimental : bool - If is experimental. Being experimental will overwrite any checks and allow the creation of the EnemyEvent object regardless of issues.

.. note::
    Experimental should always be set to False as it could lead to issues otherwise.

.. warning::

    Having RaidWide set to True and giving a value of more than 0 for nTBTarget will result in
    an *InvalidTankBusterTargetNumber* error.

**Usage**

.. code-block:: python
    
    MagicRaidWide = EnemyEvent(1, 2, 400)
    PhysicalRaidWide = EnemyEvent(3, 2, 500, IsPhysical=True)
    TankBuster = EnemyEvent(2, 2, 1000, RaidWide=False, nTBTarget=1)