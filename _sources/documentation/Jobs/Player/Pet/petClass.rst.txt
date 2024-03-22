Pet
===

The Pet class is a subclass of the Player class. It is used to represent any 
non player character summoned by a player such as : Summoner primal, Ninja shadow, etc.

The Pet object themself do not do anything and must be given an action set by the player who summons them.


**Class attribute**

.. note::

    This class also shares all the attributes of any Player object.

* Pet.Master : Player - A reference to the player who summoned this pet.

**Class functions**

.. toctree::

    petInnit
    petResetStat