Player class
============

The Player class represents a player character in a simulation. It contains information such as : HP, mana, damage done, state, stats, etc.
Every different job will be a different player object, in the sense that a BlackMage player will not have the same attributes as a Samurai player.
Only the commonly shared attributes and functions will be explored here.

**Class attributes**

Since there are a lot of attributes, they will be brocken down in different categories.

*Base attributes*

* Player.ActionSet : list[Spell] - List of actions to perform.
* Player.RoleEnum : RoleEnum - Value of the RoleEnum for this player (defines a role).
* Player.Job : JobEnum - Value of the JobEnum for this player (define a job).
* Player.ClassActions : class - An enum that holds IDs of all the actions of the class of the player.
* Player.CurrentFight : Fight - Reference to the Fight object the player is in.
* Player.playerID : int - Unique identifier of the player in the Player.CurrentFight.
* Player.PlayerName : str - Name of the player. Displayed in results.
* Player.Pet : Pet - Reference to the Pet summoned by the Player.
* Player.baseDelay : float - Base delay between every autos.
* Player.autoPointer : DOTSpell - This is a reference to a player's autos DOT object.
* Player.MaxHP : int - Max HP of the player.
* Player.Stat : dict[str : int] - Stats of the player.
* Player.baseMainStat : int - Original value of the stat 'MainStat' of the player.
* Player.Trait : float - Trait multiplicative value for the player.
* Player.f_WD : float - Damage stat value from weapon.
* Player.f_DET : float - Damage stat value from determination.
* Player.f_TEN : float - Damage stat value from tenacity.
* Player.CritRate : float - Rate of critical hit.
* Player.CritMult : float - Damage multiplier on critical hits.
* Player.DHRate : float - Rate of direct hit.
* Player.DHAuto : Damage multiplier on auto crit/dh.
* Player.JobMod : int - Job mod value for this player.

*State tracking attributes*

* Player.Mana : int - Current mana of the player.
* Player.HP : int - Current HP of the player.
* Player.EffectList : list[function] - List of all effects applied on the player at one time.
* Player.EffectCDList : list[function] - List of functions that check the countdown/duration of effects. These functions will remove an effect if it has to.
* Player.DOTList : list[DOTSpel] - List of all DOT the player is currently applying.
* Player.CastingSpell : Spell - Object of the current action being casted.
* Player.Casting : bool - True if the player is currently casting.
* Player.oGCDLock : bool - True of the player is locked from doing any oGCD.
* Player.GCDLock : bool - True if the player is locked from doing any GCD.
* Player.CastingLockTimer : float - Timer until the player can start the next cast.
* Player.oGCDLockTimer : float - Timer until the player will no longer be locked from doing oGCD (until oGCDLock is set to False).
* Player.GCDLockTimer : float - Timer until the player will no longer be locked from doing GCD (until GCDLock is set to False).
* Player.NextSpell : int - Index of the next action to perform (index in the Player.ActionSet list)
* Player.ManaTick : float - Current value of the mana tic timer.
* Player.mainStatBonus : float - Used to store in memory any gain of main stat through potions.
* Player.TrueLock : bool - If true the player is completely lock and is done performing its ActionSet. The simulator will not update the state of a player where truelock is true.
* Player.NoMoreActionLog : bool - Indicates that a log of the player not having any more actions has been created.
* Player.NoMoreAction : bool - Indicates that a player has no more actions to do. It has reached the end of its ActionSet.
* Player.PotionTimer : float - Timer of a potion effect.
* Player.currentDelay : float - Current delay between every autos.
* Player.Haste : int - Current total haste value the player has.
* Player.autoHaste : int - Current total haste the player has that only work on the delay between autos.
* Player.hasteHasChanged : bool - Set to true when an action changes the player's haste due to being applied or to expiration of an effect.
* Player.hasChangeValue : int - Amount by which haste has changed. Can be negative (meaning a lost of haste).
* Player.ShieldList : list[Shield] - List of all Shield object currently on the player.
* Player.ShieldNameList : list[str] - List of the name of all shields on the player.
* Player.EnemyDOT : list[EnemyDOT] - List of all EnemyDOT object currently on the player.
* Player.TotalEnemity : int - Total enemity the player currently has.
* Player.MagicMitigation : float - Current value of magic mitigation the player has.
* Player.PhysicalMitigation : float - Current value of physical mitigation the player has.
* Player.auras : list - List of all auras the player starts with.
* Player.buffList : list[buff] - List of all multiplicative buffs on the player.
* Player.MitBuffList : list[MitBuff] - List of all multiplicative mitigation buffs on the player.
* Player.MitBuffListName : list[str] - List of all names of the mitigation buffs currently on the player.
* Player.ReceivedHealBuffList : list[HealingBuff] - List of all multiplicative healing buffs that apply on heals the player receives.
* Player.ReceivedHealBuffNameList : list[str] - Name of all multiplicative healing buffs that apply on heals the player receives.
* Player.GivenHealBuffList : list[HealingBuff] - List of all multiplicative healing buffs that apply on heals the player gives.
* Player.GivenHealBuffNameList : list[str] - Name of all multiplicative healing buffs that apply on heals the player receives.
* Player.EffectToRemove : list[function] - List of all functions to remove from the player's EffectList list on the next check.
* Player.ArcanumTimer : float - Timer for any of the arcanum buff given to the player.
* Player.ArcanumBuff : buff - Arcanum buff object given to the player.
* Player.MeditativeBrotherhoodTimer : float - Timer for meditative brotherhood effect.
* Player.OblationTimer : float - Timer for oblation's effect.
* Player.CorundumTimer : float - Timer for Hearts of Corundum's effect.
* Player.NascentFlashTimer : float - Timer for Nascent flash's effect.
* Player.InterventionTimer : float - Timer for Intervention's effect.

*PreBakedAction related attributes*

* Player.PreBakedActionSet : list[PreBakedAction] - List of all PreBakedActions to perform.
* Player.ChainStratagemHistory : list[buffHistory] - Contains all history of an occurence of chain stratagem.
* Player.BattleLitanyHistory : list[buffHistory] - Contains all history of an occurence of battle litany.
* Player.WanderingMinuetHistory : list[buffHistory] - Contains all history of an occurence of wandering minuet.
* Player.BattleVoiceHistory : list[buffHistory] - Contains all history of an occurence of battle voice.
* Player.DevilmentHistory : list[buffHistory] - Contains all history of an occurence of devilment.
* Player.PotionHistory : list[buffHistory] - Contains all history of an occurence of a potion.
* Player.PercentBuffHistory : list[buffHistory] - Contains all history of an occurence of any multiplicative buff.

*ZIPActions related attributes*

* Player.ZIPActionSet : list[ZIPAction] - List of ZIPActions to perform.
* Player.ZIPDPSRun : list[float] - List of all ZIP runs' DPS performed.
* Player.ZIPRunPercentile : dict[str : int] - Count of the amount of runs in each percentiles.
* Player.DPSBar : dict[str : int] - Count of different DPS obtained during ZIP simulations (random simulations).

*Counter attributes*

* Player.GCDCounter : int - Amount of GCD performed.
* Player.totalTimeNoFaster : float - Total time the player has been doing actions that cannot be made faster by SpS/SkS. Used for prebakedactions.
* Player.NumberDamageSpell : int - Amount of actions done that have non zero potency.
* Player.TotalPotency : int - Total potency done by the player.
* Player.TotalDamage : int - Total damage done by the player.


.. note::

    On top of these attributes, as stated above, a player will generally have much more depending on its role and job value. If you are interested in knowing more
    about these other attributes go check the *Fight.py* page on github and locate the functions init_tank(), init_healer(), init_caster(), init_melee(), init_physicalranged() and then
    the function init_*jobname*() for further information on the attributes initialized when creating a player.

**Class functions**

.. toctree::

    playerInnit
    playerClassUpdateTimer
    playerClassUpdateCD
    playerClassUpdateLock

**Class functions for BlackMage**

.. toctree::

    playerAddFire
    playerAddIce

**Class functions for Ninja**

.. toctree::

    playerAddHuton
    playerAddNinki
    playerResetRitual

**Class functions for Reaper**

.. toctree::

    playerAddGauge
    playerAddShroud

**Class functions for Monk**

.. toctree::

    playerOpenChakra
    playerResetMasterGauge
    playerAddBestChakra
    playerBeastChakraType

**Class functions for Summoner**

.. toctree::

    playerResetPrimalEffect