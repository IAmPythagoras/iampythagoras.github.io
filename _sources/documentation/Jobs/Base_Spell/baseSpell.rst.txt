Base_Spell
==========

The *Base_Spell* module is responsible for the logic of all actions. It takes care of the logic of when an action is being casted, is casted, etc.

This module contains the following class : Spell, ZIPAction, PreBakedAction, buff, buffHistory, DOTSpell, HOTSpell, Auto_Attack, Queen_Auto, Melee_Auto, Ranged_Auto and Monk_AA.

**Import**

.. code-block:: python

    from ffxivcalc.Jobs.Base_Spell import Spell, ZIPAction, PreBakedAction, buff, buffHistory, DOTSpell, HOTSpell, Auto_Attack, Queen_Auto, Melee_Auto, Ranged_Auto, Monk_AA

**Module class**

.. toctree::

    spellObj/spellClass
    PreBakedAction/preBakedActionClass
    ZipAction/zipActionClass
    Buff/buffClass
    BuffHistory/buffHistoryClass
    BuffPercentageHistory/buffPercentageHistoryClass