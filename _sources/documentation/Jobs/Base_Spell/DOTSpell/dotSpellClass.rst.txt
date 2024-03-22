DOTSpell
========

This class represents a DOT applied on a target. This class takes care of applying the damage at the right time, buff snapshots and other counter.

This class is a sublcass of Spell.

**Class attributes**

* DOTSpell.DOTTimer : float - Internal timer of the DOT.
* DOTSpell.isPhysical : bool - If the DOT applies physical damage. If False then the DOT applies magical damage.
* DOTSpell.isGround : bool - If the DOT comes from a ground AOE. For example, doton/salted earth.
* DOTSpell.CritBonus : float - Critical hit chance bonus on the DOT.
* DOTSpell.DHBonus : float - Direct hit chance bonus on the DOT.
* DOTSpell.MultBonus : list[buff] - All multiplicative buff object applied on the DOT.
* DOTSpell.potSnapshot : bool - True if a potion's effect is applied on the DOT.
* DOTSpell.onceThroughFlag : bool - A flag indicating if the DOT has snapshotted buffs or not.
* DOTSpell.ticAmount : int - Counter of how many tic the DOT has had.

**Class functions**

.. toctree::

    dotSpellInit
    dotSpellResetBuffSnapshot
    dotSpellSetBuffSnapshot 
    dotSpellCheckDOT

**Subclass**

.. toctree::

    HOTSpell/hotSpellClass
    Auto_Attack/autoAttackClass


