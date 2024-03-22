PreBakedAction
==============

This is a preprocessed action. These actions record buffs and other effects that happen and they allow
the recomputation of the damage of the action. PreBakedAction allows to simulate for a given GCD timer value and then recompute
the DPS of a whole simulation where we change non speed related values much quicker than by resimulating the whole simulation.

It is similar to a ZIPAction, but it has less preprocessing than a ZIPAction does.

PreBakedActions are used with the Rotation BiS solver to quickly compute different DPS given
a gear set.

**Class attributes**

* PreBakedAction.IsTank : bool - If the player doing this PreBakedAction is a tank.
* PreBakedAction.MainStatPercentageBonus : float - PercentageBonus of the MainStat (given by team composition).
* PreBakedAction.buffList : list[buff] - List of all buffs on the action.
* PreBakedAction.TraitBonus : float - Damage bonus from trait (Ex: 1.3).
* PreBakedAction.type : int - Type of the original action. Refer to Spell class for different type value.
* PreBakedAction.timeStamp : float - time stamp of the action.
* PreBakedAction.Potency : int - Potency of the action.
* PreBakedAction.AutoCrit : bool - True if action is auto crit.
* PreBakedAction.AutoDH : bool - True if action is auto DH. If is auto direct crit then both are true.
* PreBakedAction.AutoCritBonus : float - Multiplicative bonus to damage due to auto crit (come from bonus crit).
* PreBakedAction.AutoDHBonus : float - Multiplicative bonus do damage on auto crit due to DH.
* PreBakedAction.isFromPet : bool - True if is a Pet action.
* PreBakedAction.isGCD : bool - True if is a GCD.
* PreBakedAction.spellDPSBuff : float - Multiplicative bonus due to spell.
* PreBakedAction.CritBonus : float - Critical hit bonus on the action.
* PreBakedAction.DHBonus : float - Direct Hit bonus on the action.
* PreBakedAction.PercentageBonus : list[float] - List of all damage mult bonus coming from buff. This list is dynamically updated once the function Fight.SimulatePreBakedFight() is called as the code will append the required multiplicative buff to it based on the buff present in PreBakedAction.buffList and others.
* PreBakedAction.potionIsActive : bool - True if this action is done under a potion effect.
* PreBakedAction.isWildFire : bool - True if the action is wildfire.

**Class functions**

.. toctree::

    preBakedActionInit
    preBakedActionResetPercentageBonus
    preBakedActionComputeExpectedDamage
    preBakedActionComputeRandomDamage
