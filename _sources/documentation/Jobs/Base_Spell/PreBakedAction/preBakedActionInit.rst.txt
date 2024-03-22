PreBakedAction.__init__()
=========================

This is the constructor of the class PreBakedAction.

**Parameters**

* IsTank : bool - If the action comes from a tank.
* MainStatPercentageBonus : float - PercentageBonus of the MainStat (given by team composition).
* buffList : list[buff] - List of all buffs on the action.
* TraitBonus : float - Damage bonus from trait (Ex: 1.3).
* Potency : int - Potency of the action.
* type : int - Type of the original action. Refer to Spell class for different type value.
* timeStamp : float - time stamp of the action.
* nonReducableStamp : float - Unused argument. Leave value of 0.
* reducableStamp : float - Unused argument. Leave value of 0.
* AutoCrit : bool - True if action is auto crit.
* AutoDH : bool - True if action is auto DH. If is auto direct crit then both are true.
* isFromPet : bool - True if is a Pet action.
* isGCD : bool - True if is a GCD.
* spellDPSBuff : float - Multiplicative buff to damage (default 1)

**Usage**

.. code-block:: python

    newPreBakedAction = PreBakedAction( False, 
                                        Player.CurrentFight.TeamCompositionBonus,
                                        [], 
                                        Player.Trait, 
                                        200, 
                                        1,
                                        Player.CurrentFight.TimeStamp if Player.CurrentFight.FightStart else 0,
                                        0, 
                                        0,
                                        AutoCrit=True, 
                                        AutoDH=False,
                                        isFromPet=False, 
                                        isGCD=True,
                                        spellDPSBuff=1.2)