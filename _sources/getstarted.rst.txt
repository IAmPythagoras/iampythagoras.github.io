Introduction
============

Firstly, in order to install this library execute the following function in your command prompt:

.. code-block:: text

    pip install ffxivcalc

In this first page, it will be explained to you how to simulate your first fight using the **ffxivcalc** library. 

Fight Class
-----------

The *Fight* class is one of the most important in the whole library. An instance of *Fight* represents the simulator and contains
all the logic responsible for the execution of the simulation. It contains information such as :

* A list of player character present in the simulation
* A reference to the Enemy of the simulation, aka the boss of a raid
* Time stamp of the simulation
* Time limit of the simulation
* A list of all *failedEvents*
* etc.

In short, an instance *Fight* is like a conductor in an orchestra and directs the whole flow
of the simulation and makes sure everything goes correctly.

When you want to simulate a fight, you have to first create an instance of *Fight*. 
Here is an example of how to do so:

.. code-block:: python

    from ffxivcalc.Fight import Fight
    from ffxivcalc.Enemy import Enemy

    newEnemy = Enemy() # Creating new Enemy instance
    ShowGraph = True # We want the simulator to generate graphs

    newFight = Fight(newEnemy, ShowGraph) # Creating new Fight instance

    newFight.RequirementOn = True # Does NOT ignore requirement during simulation
    newFight.IgnoreMana = False # Does NOT ignore Mana requirement during simulation

As you can see in the above example, we are also creating an instance of the class *Enemy*. For now you don't need
to think much about this class. However, just like any raid needs a boss, a simulation needs an enemy. Furthermore,
we also give the constructor of *Fight* a paramter *ShowGraph* which is simply a boolean value which if set true 
tells the simulator to generate graphs at the end.

A *Fight* instance also contains other parameters for the simulation such as :

* *RequirementOn* -> If set to false the simulator ignores the requirements of an action.
* *IgnoreMana* -> If set to true, the simulator ignore the mana requirements of an action.

These can be changed according to your needs.

.. note::
    Both *RequirementOn* and *IgnoreMana* have a default value of true.

Now that our *Fight* instance is created, we need to add some players to it.

Player class
------------

The player class represents any player character in the simulation. It contains information such as :

* The list of actions we want the player to do in the simulation.
* A list of all effect on the player at any time.
* Current state of the player (If the player is casting, if it can cast a GCD, etc.)
* Current HP and mana of the player
* The *Role* and *Job* of a player
* etc.


In order to add a player to the *Fight* instance we need to create a *Player* instance and add it to the fight.

.. code-block:: python

    from ffxivcalc.Jobs.Player import Player # Importing player class
    from ffxivcalc.Jobs.PlayerEnum import JobEnum # Importing JobEnum

    ActionSet = [] # List containing actions to be performed. Can be left empty
    EffectList = [] # List of all effect on the player at start. Can be left empty
    Stat = {"MainStat": 2945, "WD":126, "Det" : 1451, "Ten" : 400, "SS": 840, "SkS" : 400, "Crit" : 2386, "DH" : 1307} # Stats for BlackMage


    newBlackMage = Player(ActionSet, EffectList, Stat, JobEnum.BlackMage) # Creating player instance

When creating a *Player* instance we need to give the constructor 4 inputs:

* *ActionSet* -> List of all actions performed by the player.
* *EffectList* -> List of all effects on the player at start, can be left empty.
* *Stat* -> Dictionnary containing the stats of the player. Follow the same structure as in the above example.
* *JobEnum* -> An enum indicating what Job the player is.

.. note::
    *JobEnum* is an enum implemented to distinguate between Jobs. You don't have to be bothered by the exact
    implementation, but you can read more about it HERE.

.. note::
    The *EffectList* given when creating the *Player* instance will generally be left empty. You can read HERE
    how to and why to not have it empty.


The *Player* instance we just created has no actions to do. In order to do so we have to fill up the *ActionSet* with *Spell*
objects.

Spell class
-----------

The *Spell* class represents an action a player can do. In the case of a BlackMage, actions would be
*Fire I*, *Fire IV*, *Xenoglossy*, etc. Furthermore, there are 3 different types of actions or spell any player can do.

Base Spell
^^^^^^^^^^

Actions that can be done by any players. The two mainly used *Base_Spell* actions are :

* *potion* : This action makes the player take a potion. Boosting its *MainStat* just like in the game.
* *WaitAbility(waitingTime : float)* : This action makes the player wait for the specified amount of time.

Role Spell
^^^^^^^^^^

Actions that can be done by players of the same *Role*. The different roles are *Casters*, *PhysicalRanged*, *Melee*, *Healer*, *Tank*.
Examples of *Role* actions are *Swiftcast*, *ArmLength*, *Esuna*, *Peloton*, *Rampart*, etc.

Job_Spell
^^^^^^^^^

Actions that can be done by players of a specific *Job*. *Job*'s could be *BlackMage*, *Machinist*, *Ninja*, *Scholar*, *Gunbreaker*, etc.

Here is how you would create an *ActionSet* for the player :

.. code-block:: python

    from ffxivcalc.Jobs.Caster.Blackmage.BlackMage_Spell import * # Importing the Blackmage Actions
    from ffxivcalc.Jobs.Caster.Caster_Spell import *    # Importing the roles action for Caster
    from ffxivcalc.Jobs.Base_Spell import Potion, WaitAbility # Importing the Base actions

    newBlackMage.ActionSet = [SharpCast, WaitAbility(20),Fire3, Thunder3, Fire4, Triplecast, Fire4, Potion, 
    Fire4, Amplifier, LeyLines, Fire4, SharpCast, Swiftcast, Despair, Manafront, Triplecast, Fire4, Despair]

.. note::
    The default path to import any *Role* actions is *ffxivcalc.Jobs.__ROLE__.__ROLE___Spell* and the default path to import
    any *Job* specific actions is *ffxivcalc.Jobs.__Role__.__Job__.__Job___Spell*.


As you can see, this action set is asking the player to perform an incomplete BlackMage opener. You can see we are using
the *Base* action *WaitAbility()* and *Potion*, the *Role* action *Swiftcast* and the *Job* action such as *Fire IV*. 


Now that the *Player* object has an *ActionSet*, we simply need to add the player to the *Fight* instance. 

.. code-block:: python

    newFight.AddPlayer([newBlackMage]) # Adding newBlackMage to newFight. Input must be a list and can contain
    # more than one Player object.

.. warning::
    When using the *AddPlayer* function on a *Fight* object, it is needed to give a list as input. The list can have multiple
    players object and it will add all player objects in the list given as input to the function.

Now that we have a *Fight* instance with a *Player* instance that has a non-empty *ActionSet* we can finally do our first simulation.

Fight.SimulateFight()
---------------------

In order to do so, we simply need to call the class function *SimulateFight()* on our *Fight* instance.

.. code-block:: python

    TimeUnit = 0.01 # Unit of time per frame
    TimeLimit = 500 # Max running time of the simulation (time IN the simulation)

    # Simulation parameters
    newFight.RequirementOn = True # Will check for actions requirement
    newFight.IgnoreMana = False # Will check for mana
    vocal = True # Want to output data in text

    newFight.SimulateFight(TimeUnit, TimeLimit, vocal) # Simulating the fight

The *SimulateFight()* class function requires 3 inputs:

* *TimeUnit* -> Smallest time unit in seconds in the simulation. The simulator will advance by that much every main loop.
* *TimeLimit* -> Maximum time the simulation will run for in seconds.
* *vocal* -> Boolean value. If true the simulator will show the data in graphs and/or text.

.. warning::

    The recommended value for *TimeUnit* is 0.01 . Different values of this parameter could result in different number
    output from the simulator.

.. warning::

    The value given in *TimeLimit* corresponds to the IN SIMULATION time, and not to the actual time. Meaning that if *TimeLimit* = 500,
    the simulation will stop if its time stamp ever reaches 500 and not if there has been 500 in real life seconds that have gone by.

After running all of the above code, you should see this text and have at least this graph show up.

.. code-block:: text

    The Fight finishes at: 16.23
    The Total Potency done by player BlackMage was : 4499.0
    This same player had a Potency Per Second of: 277.2
    This same Player had an average of 236.79 Potency/Spell
    This same player did 9 GCD.
    The DPS is : 14100.31
    =======================================================
    The Enemy has received a total potency of: 4499.0
    The Potency Per Second on the Enemy is: 277.2
    The Enemy's total DPS is 14100.31

.. image:: getstartedgraph.png
  :width: 800
  :alt: DPS and PPS graphs outputed by the simulator

You have now ran your first simulation using **ffxivcalc**! This is all the basis you need to know
in order to simulate fights. The rest of this tutorial will be some more code examples, after which more complex
customization will be discussed.

More code examples
------------------

Simulating a BlackMage but with *RequirementsOn* = False
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Say one wants to simulate an action set that is not possible in the base game. Say this is the action sets one wishes to perform on a BlackMage:

.. code-block:: python

    newBlackMage.ActionSet = [Fire3, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy]

Obviously such a set of action is not possible in the game. But here we can dream and see the result. The only thing we need to do
is to let *RequirementOn* be false.

.. code-block:: python

    from ffxivcalc.Fight import Fight
    from ffxivcalc.Enemy import Enemy

    newEnemy = Enemy()
    ShowGraph = False # We don't want the simulator to generate graphs

    newFight = Fight(newEnemy, ShowGraph) # Creating new Fight instance

    from ffxivcalc.Jobs.Player import Player # Importing player class
    from ffxivcalc.Jobs.PlayerEnum import JobEnum # Importing JobEnum

    ActionSet = [] # List containing actions to be performed. Can be left empty
    EffectList = [] # List of all effect on the player at start. Can be left empty
    Stat = {"MainStat": 2945, "WD":126, "Det" : 1451, "Ten" : 400, "SS": 840, "Crit" : 2386, "DH" : 1307} # Stats for BlackMage

    newBlackMage = Player(ActionSet, EffectList, Stat, JobEnum.BlackMage)

    from ffxivcalc.Jobs.Caster.Blackmage.BlackMage_Spell import *
    from ffxivcalc.Jobs.Caster.Caster_Spell import *
    from ffxivcalc.Jobs.Base_Spell import Potion, WaitAbility

    newBlackMage.ActionSet = [Fire3, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy, Xenoglossy]

    newFight.AddPlayer([newBlackMage])

    TimeUnit = 0.01 # Unit of time per frame
    TimeLimit = 500 # Max running time of the simulation (time IN the simulation)

    # Simulation parameters
    newFight.RequirementOn = False # Will check for actions requirement
    newFight.IgnoreMana = False # Will check for mana
    vocal = True # Want to output data in text

    newFight.SimulateFight(TimeUnit, TimeLimit, vocal) # Simulating the fight


Output :

.. code-block:: text

    The Fight finishes at: 16.94
    ========================
    Results for BlackMage ID - 1 :
    DPS : 20820.84 PPS : 430.93 TP : 7300 GCD : 9 TD : 352705

    =================
    Total DPS : 20820.84    Total PPS : 430.93      Total Potency : 7300

If instead we had not changed *RequirementOn* to False, the simulator would have outputed this:

.. code-block:: text

    The simulation ran into a problem. You can disable requirements by setting 'Fight.RequirementOn' to 'False'.
    =================
    List of failed fatal requirements :
    Failed Fatal Requirement : PolyglotRequirement Timestamp : 0

    The Fight finishes at: 0
    ========================
    Results for BlackMage ID - 1 :
    DPS : 54316.0 PPS : 1140.0 TP : 1140 GCD : 2 TD : 54316

    =================
    Total DPS : 54316.0     Total PPS : 1140.0      Total Potency : 1140

As you can see the fight finishes early and it tells the user the name of the first fatal failed requirement. In this case it is *PolyglotRequirement*.

.. warning::

    Any value outputted by the simulation when a requirement failed might be wrong because of how the simulator handles some values. Because of that
    do not take a failed simulation's number to be accurate. Instead just put *RequirementOn* to be false and then run the simulation.

The same kind of things can be done by letting *IgnoreMana* = True.

Simulate a Dancer and Ninja opener with the Ninja being the Dancer's dance partner.
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

One thing to make sure you understand here is that some actions are functions that return *Spell* object. Such examples
would be the *ClosedPosition(target)* actions of Dancer that makes the target its dance partner. Similar actions include
*DragonSight* of a dragoon and an astrologian giving cards.

Code simulating a dancer and a ninja doing their opener :

.. code-block:: python

    from ffxivcalc.Fight import Fight
    from ffxivcalc.Enemy import Enemy

    newEnemy = Enemy()
    ShowGraph = True

    newFight = Fight(newEnemy, ShowGraph) # Creating new Fight instance

    from ffxivcalc.Jobs.Player import Player # Importing player class
    from ffxivcalc.Jobs.PlayerEnum import JobEnum # Importing JobEnum

    NINStat = {"MainStat": 2921, "WD":126, "Det" : 1669, "Ten" : 400, "SS": 400, "SkS" : 400, "Crit" : 2399, "DH" : 1511} # Stats for Ninja
    DNCStat = {"MainStat": 2949, "WD":126, "Det" : 1721, "Ten" : 400, "SS": 400, "SkS" : 536, "Crit" : 2387, "DH" : 1340} # Stats for Dancer

    NinjaPlayer = Player([], [], NINStat, JobEnum.Ninja) # Creating Ninja player
    DancerPlayer = Player([], [], DNCStat, JobEnum.Dancer) # Creating Dancer player

    from ffxivcalc.Jobs.Melee.Ninja.Ninja_Spell import * # Importing ninja actions
    from ffxivcalc.Jobs.Melee.Melee_Spell import * # Importing melee actions
    from ffxivcalc.Jobs.Ranged.Dancer.Dancer_Spell import * # Importing dancer actions
    from ffxivcalc.Jobs.Ranged.Ranged_Spell import * # Importing Ranged actions
    from ffxivcalc.Jobs.Base_Spell import Potion, WaitAbility

    NinjaPlayer.ActionSet = [WaitAbility(10),Jin, Chi, Ten, Huton, Hide, Ten, Chi, Jin, WaitAbility(5), 
    Suiton, Kassatsu, SpinningEdge, GustSlash, Mug, Bunshin, PhantomKamaitachi, 
    TrickAttack, AeolianEdge, DreamWithinADream, Ten, Jin, HyoshoRanryu, Ten, Chi,
    Raiton, TenChiJin, Ten2, Chi2, Jin2, Meisui, FleetingRaiju, Bhavacakra,
    FleetingRaiju, Bhavacakra, Ten, Chi, Raiton, FleetingRaiju ]

    # Ninja action set

    DancerPlayer.ActionSet = [ClosedPosition(NinjaPlayer),StandardStep, Pirouette, Jete, WaitAbility(15), StandardFinish, TechnicalStep, 
    Pirouette, Jete, Entrechat, Emboite, TechnicalFinish, Devilment, StarfallDance, Flourish, 
    FanDance3, Tillana, FanDance4, FountainFall, FanDance1, FanDance3, StandardStep, Jete, Pirouette, StandardFinish]

    # Dancer action set


    newFight.AddPlayer([DancerPlayer, NinjaPlayer]) # Adding players to the fight

    TimeUnit = 0.01 # Unit of time per frame
    TimeLimit = 500 # Max running time of the simulation (time IN the simulation)

    # Simulation parameters
    newFight.RequirementOn = True # Will check for actions requirement
    newFight.IgnoreMana = False # Will check for mana
    vocal = True # Want to output data in text

    newFight.SimulateFight(TimeUnit, TimeLimit, vocal) # Simulating the fight

.. note::

    As you can see, when using the action *ClosedPosition* in the dancer's action set, I am giving as input *NinjaPlayer* to let
    the action know that the dancer is targetting the ninja when casting closed position.

It outputs this :

.. code-block:: text

    The Fight finishes at: 26.71
    ========================
    Results for Dancer ID - 1 :
    DPS : 11120.33 PPS : 209.66 TP : 5600 GCD : 17 TD : 297024
    Procs/Gauge result (Used/Expected) :
    Silken Symettry : 0/0 Silken Flow : 0/0
    Fourfold Feather : 1/0.5 Threefold Fan : 2/1.5
    =================
    Results for Ninja ID - 2 :
    DPS : 19494.05 PPS : 433.92 TP : 11590 GCD : 28 TD : 520686

    =================
    Total DPS : 30614.38    Total PPS : 643.58      Total Potency : 17190

.. image:: dancer_nin_opener.png
  :width: 800
  :alt: DPS and PPS graphs outputed by the simulator


.. note::
    For *Jobs* where procs are an important part of it the simulator will also output data regarding the number
    of used procs and number of expected procs.

.. warning::
    The simulation starts as soon as 1 player does damage and stops either if it detects a fatal failed requirement or
    if all players are done with their action set. Because of that, you have to make sure every job starts doing damage at the same time.



Simulating two Ninjas doing the exact same opener
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python

    from ffxivcalc.Fight import Fight
    from ffxivcalc.Enemy import Enemy

    newEnemy = Enemy()
    ShowGraph = False

    newFight = Fight(newEnemy, ShowGraph) # Creating new Fight instance

    from ffxivcalc.Jobs.Player import Player # Importing player class
    from ffxivcalc.Jobs.PlayerEnum import JobEnum # Importing JobEnum

    NINStat = {"MainStat": 2921, "WD":126, "Det" : 1669, "Ten" : 400, "SS": 400, "SkS": 536, "Crit" : 2399, "DH" : 1511} # Stats for Ninja
    DNCStat = {"MainStat": 2949, "WD":126, "Det" : 1721, "Ten" : 400, "SkS": 536, "SS": 400, "Crit" : 2387, "DH" : 1340} # Stats for Dancer

    NinjaPlayer1 = Player([], [], NINStat, JobEnum.Ninja) # Creating Ninja player
    NinjaPlayer2 = Player([], [], NINStat, JobEnum.Ninja) # Creating Ninja player
    #DancerPlayer = Player([], [], DNCStat, JobEnum.Dancer) # Creating Dancer player

    from ffxivcalc.Jobs.Melee.Ninja.Ninja_Spell import * # Importing ninja actions
    from ffxivcalc.Jobs.Melee.Melee_Spell import * # Importing melee actions
    from ffxivcalc.Jobs.Base_Spell import Potion, WaitAbility

    NinjaPlayer1.ActionSet = [Jin, Chi, Ten, Huton, Hide, Ten, Chi, Jin, WaitAbility(5), 
    Suiton, Kassatsu, SpinningEdge, GustSlash, Mug, Bunshin, PhantomKamaitachi, 
    TrickAttack, AeolianEdge, DreamWithinADream, Ten, Jin, HyoshoRanryu, Ten, Chi,
    Raiton, TenChiJin, Ten2, Chi2, Jin2, Meisui, FleetingRaiju, Bhavacakra,
    FleetingRaiju, Bhavacakra, Ten, Chi, Raiton, FleetingRaiju ]

    NinjaPlayer2.ActionSet = [Jin, Chi, Ten, Huton,Hide, Ten, Chi, Jin, WaitAbility(5), 
    Suiton, Kassatsu, SpinningEdge, GustSlash, Mug, Bunshin, PhantomKamaitachi, 
    TrickAttack, AeolianEdge, DreamWithinADream, Ten, Jin, HyoshoRanryu, Ten, Chi,
    Raiton, TenChiJin, Ten2, Chi2, Jin2, Meisui, FleetingRaiju, Bhavacakra,
    FleetingRaiju, Bhavacakra, Ten, Chi, Raiton, FleetingRaiju  ]

    newFight.AddPlayer([NinjaPlayer1,NinjaPlayer2]) # Adding players to the fight

    TimeUnit = 0.01 # Unit of time per frame
    TimeLimit = 500 # Max running time of the simulation (time IN the simulation)

    # Simulation parameters
    newFight.RequirementOn = True # Will check for actions requirement
    newFight.IgnoreMana = False # Will check for mana
    vocal = True # Want to output data in text

    newFight.SimulateFight(TimeUnit, TimeLimit, vocal) # Simulating the fight

.. note::

    Giving the same *Stat* dictionnary to two different player is all right since the code makes a *deepcopy* of the dictionnary
    when creating the player object. 

It ouputs :

.. code-block:: text

    The Fight finishes at: 25.09
    ========================
    Results for Ninja ID - 1 :
    DPS : 17381.19 PPS : 458.35 TP : 11500 GCD : 28 TD : 436094

    =================
    Results for Ninja ID - 2 :
    DPS : 17391.07 PPS : 458.35 TP : 11500 GCD : 28 TD : 436342

    =================
    Total DPS : 34772.26    Total PPS : 916.7       Total Potency : 23000

As you can see, both ninjas do not have the exact same DPS. The reason for that lies within how the simulator works. 
In fact, the simulator process each player in order. Meaning that the DPS gain for the second ninja is because
the first ninja casts and applies mug before the 2nd one does. Giving the second ninja a slight DPS bonus over the first one since
the second mug's damage is slightly buffed by the first one. This is an edge case that will always be present since it would be quite hard to fix.

You can in fact see that they both have the same total potency, but that only their DPS differs.

Simulating a standard 8 man raid doing their opener
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Now let us try the big advantage of this simulator : to simulate a whole raid group. The team composition will be 
DRK - GNB - RDM - NIN - DRG - DNC - SCH - WHM and they will all be doing their respective opener.

Here is the code : 

.. code-block:: python

    from ffxivcalc.Fight import Fight
    from ffxivcalc.Enemy import Enemy

    newEnemy = Enemy()
    ShowGraph = True

    newFight = Fight(newEnemy, ShowGraph) # Creating new Fight instance

    from ffxivcalc.Jobs.Player import Player # Importing player class
    from ffxivcalc.Jobs.PlayerEnum import JobEnum # Importing JobEnum
    # Caster
    RDMStat = {"MainStat": 2947, "WD":126, "Det" : 1548, "Ten" : 400, "SS": 495,"SkS" : 400, "Crit" : 2397, "DH" : 1544} # Stats for RedMage

    # Healer
    SCHStat = {"MainStat": 2931, "WD":126, "Det" : 1750, "Ten" : 400, "SS": 1473, "SkS" : 400, "Crit" : 2351, "DH" : 436} # Stats for Scholar
    WHMStat = {"MainStat": 2945, "WD":126, "Det" : 1792, "Ten" : 400, "SS": 839, "SkS" : 400, "Crit" : 2313, "DH" : 904} # Stats for WhiteMage

    # Physical Ranged
    DNCStat = {"MainStat": 2949, "WD":126, "Det" : 1721, "Ten" : 400, "SkS": 536, "SS" : 400,"Crit" : 2387, "DH" : 1340} # Stats for Dancer

    # Melee
    NINStat = {"MainStat": 2921, "WD":126, "Det" : 1669, "Ten" : 400, "SS": 400,"SkS" : 400, "Crit" : 2399, "DH" : 1511} # Stats for Ninja
    DRGStat = {"MainStat": 2949, "WD":126, "Det" : 1545, "Ten" : 400, "SS": 400,"SkS" : 400, "Crit" : 2462, "DH" : 1577} # Stats for Dragoon

    # Tank
    DRKStat = {"MainStat": 2910, "WD":126, "Det" : 1844, "Ten" : 751, "SS": 400,"SkS" : 400, "Crit" : 2377, "DH" : 1012} # Stats for DarkKnight
    GNBStat = {"MainStat": 2891, "WD":126, "Det" : 1883, "Ten" : 631, "SkS": 650,"SS" : 400, "Crit" : 2352, "DH" : 868} # Stats for Gunbreaker

    # Caster player object
    RDMPlayer = Player([], [], RDMStat, JobEnum.RedMage)

    # Healer player object
    SCHPlayer = Player([], [], SCHStat, JobEnum.Scholar)
    WHMPlayer = Player([], [], WHMStat, JobEnum.WhiteMage)

    # Physical Ranged
    DNCPlayer = Player([], [], DNCStat, JobEnum.Dancer)

    # Melee
    NINPlayer = Player([], [], NINStat, JobEnum.Ninja)
    DRGPlayer = Player([], [], DRGStat, JobEnum.Dragoon)

    # Tank
    DRKPlayer = Player([], [], DRKStat, JobEnum.DarkKnight)
    GNBPlayer = Player([], [], GNBStat, JobEnum.Gunbreaker)

    from ffxivcalc.Jobs.Melee.Ninja.Ninja_Spell import * # Importing ninja actions
    from ffxivcalc.Jobs.Melee.Dragoon.Dragoon_Spell import * # Importing dragoon actions
    from ffxivcalc.Jobs.Melee.Melee_Spell import * # Importing melee actions

    from ffxivcalc.Jobs.Ranged.Dancer.Dancer_Spell import * # Importing dancer actions
    from ffxivcalc.Jobs.Ranged.Ranged_Spell import * # Importing physical ranged actions

    from ffxivcalc.Jobs.Caster.Redmage.Redmage_Spell import * # Importing redmage actions
    from ffxivcalc.Jobs.Caster.Caster_Spell import * # Importing caster actions

    from ffxivcalc.Jobs.Healer.Scholar.Scholar_Spell import * # Importing scholar actions
    from ffxivcalc.Jobs.Healer.Whitemage.Whitemage_Spell import * # Importing whitemage actions
    from ffxivcalc.Jobs.Healer.Healer_Spell import * # Importing healer actions

    from ffxivcalc.Jobs.Tank.DarkKnight.DarkKnight_Spell import * # Importing darkknight actions
    from ffxivcalc.Jobs.Tank.Gunbreaker.Gunbreaker_Spell import * # Importing gunbreaker actions
    from ffxivcalc.Jobs.Tank.Tank_Spell import * # Importing tank actions

    from ffxivcalc.Jobs.Base_Spell import Potion, WaitAbility

    # Caster
    RDMPlayer.ActionSet = [WaitAbility(15), Verthunder, Verareo, Swiftcast,Acceleration, Verthunder, Verthunder, Embolden, Manafication, EnchantedRiposte, Fleche, EnchantedZwerchhau, Contre, EnchantedRedoublement, Corps, Engagement, Verholy, Corps, Engagement, Scorch, Resolution, Verfire, Verthunder, Verstone, Verareo, Jolt, Verthunder, Fleche]

    # Healer
    SCHPlayer.ActionSet = [WaitAbility(18.5),Broil, Biolysis, Aetherflow, Broil, Swiftcast, Broil, ChainStratagem, EnergyDrain, Broil, EnergyDrain, Broil, EnergyDrain, Broil, Dissipation, Broil, EnergyDrain, Broil, EnergyDrain, Broil, EnergyDrain]
    WHMPlayer.ActionSet = [WaitAbility(18.5),Glare, Dia, Glare, Glare, PresenceOfMind, Glare, Assize, Glare, Glare, Glare, Glare, Glare, Glare, Glare, Glare, Glare, Glare, Glare]

    # Physical Ranged 
    DNCPlayer.ActionSet = [ClosedPosition(NINPlayer),StandardStep, Pirouette, Jete, WaitAbility(15), StandardFinish, TechnicalStep, Pirouette, Jete, Entrechat, Emboite, TechnicalFinish, Devilment, StarfallDance, Flourish, FanDance3, Tillana, FanDance4, FountainFall, FanDance1, FanDance3, StandardStep, Jete, Pirouette, StandardFinish]

    # Melee
    DRGPlayer.ActionSet = [WaitAbility(20),TrueThrust, Disembowel, LanceCharge, DragonSight(NINPlayer), ChaoticSpring, BattleLitany, WheelingThrust, Geirskogul, LifeSurge, FangAndClaw, HighJump, RaidenThrust, DragonFireDive, VorpalThrust, LifeSurge, MirageDive, HeavenThrust, SpineshafterDive, FangAndClaw, SpineshafterDive, WheelingThrust, RaidenThrust, WyrmwindThrust, Disembowel, ChaoticSpring, WheelingThrust]
    NINPlayer.ActionSet = [WaitAbility(10), Jin, Chi, Ten, Huton, Hide, Ten, Chi, Jin, WaitAbility(5), Suiton, Kassatsu, SpinningEdge, GustSlash, Mug, Bunshin, PhantomKamaitachi, TrickAttack, AeolianEdge, DreamWithinADream, Ten, Jin, HyoshoRanryu, Ten, Chi, Raiton, TenChiJin, Ten2, Chi2, Jin2, Meisui, FleetingRaiju, Bhavacakra, FleetingRaiju, Bhavacakra, Ten, Chi, Raiton, FleetingRaiju ]

    # Tank 
    DRKPlayer.ActionSet = [WaitAbility(16), BloodWeapon, WaitAbility(4), HardSlash, EdgeShadow, Delirium, SyphonStrike, Souleater, LivingShadow, SaltedEarth, HardSlash, Shadowbringer, EdgeShadow, Bloodspiller, CarveSpit, Plunge, Bloodspiller, Shadowbringer, EdgeShadow, Bloodspiller, SaltDarkness, EdgeShadow, SyphonStrike, Plunge, EdgeShadow]
    GNBPlayer.ActionSet = [WaitAbility(20),LightningShot, KeenEdge, BrutalShell, NoMercy, Bloodfest, GnashingFang, JugularRip, SonicBreak, BlastingZone, BowShock, DoubleDown, RoughDivide, SavageClaw, AbdomenTear, RoughDivide, WickedTalon, EyeGouge, SolidBarrel, BurstStrike, Hypervelocity, KeenEdge]




    newFight.AddPlayer([GNBPlayer, DRKPlayer, SCHPlayer, WHMPlayer, RDMPlayer, DNCPlayer, DRGPlayer, NINPlayer]) # Adding players to the fight

    TimeUnit = 0.01 # Unit of time per frame
    TimeLimit = 500 # Max running time of the simulation (time IN the simulation)

    # Simulation parameters
    newFight.RequirementOn = True # Will check for actions requirement
    newFight.IgnoreMana = False # Will check for mana
    vocal = True # Want to output data in text

    newFight.SimulateFight(TimeUnit, TimeLimit, vocal) # Simulating the fight

Outputs :

.. code-block:: text

    The Fight finishes at: 34.97
    ========================
    Results for Gunbreaker ID - 1 :
    DPS : 8940.86 PPS : 240.21 TP : 8400 GCD : 11 TD : 312662

    =================
    Results for DarkKnight ID - 2 :
    DPS : 10964.91 PPS : 317.13 TP : 11090 GCD : 8 TD : 383443

    =================
    Results for Scholar ID - 3 :
    DPS : 5450.7 PPS : 113.1 TP : 3955 GCD : 10 TD : 190611

    =================
    Results for WhiteMage ID - 4 :
    DPS : 7905.06 PPS : 163.28 TP : 5710 GCD : 16 TD : 276440

    =================
    Results for RedMage ID - 5 :
    DPS : 12949.93 PPS : 249.64 TP : 8730 GCD : 16 TD : 452859
    Procs/Gauge result (Used/Expected) :
    Verfire : 1/3.5 Verstone : 1/2.0
    =================
    Results for Dancer ID - 6 :
    DPS : 10018.44 PPS : 167.86 TP : 5870 GCD : 17 TD : 350345
    Procs/Gauge result (Used/Expected) :
    Silken Symettry : 0/0 Silken Flow : 0/0
    Fourfold Feather : 1/0.5 Threefold Fan : 2/1.5
    =================
    Results for Dragoon ID - 7 :
    DPS : 11957.94 PPS : 226.34 TP : 7915 GCD : 14 TD : 418169

    =================
    Results for Ninja ID - 8 :
    DPS : 17974.81 PPS : 339.15 TP : 11860 GCD : 28 TD : 628579

    =================
    Total DPS : 86162.65    Total PPS : 1816.7      Total Potency : 63530


.. image:: full_team_opener.png
  :width: 800
  :alt: DPS and PPS graphs outputed by the simulator

.. note::

    The simulator automatically computes the team composition bonus depending on what role is present 
    in the fight.

In this case the openers were set up to simulate a 20 seconds countdown before starting to do damage.

The generated graphics (either DPS distribution or DPS Vs. Time) will be saved in the same directory where the script was executed.

The rest of the documentation will focus on stuff that is not mandatory. But feel free to stop by anyway!