Player.computeActionTimer()
===========================

Computes and sets the value of Spell.CastTime and Spell.RecastTime of the given Spell object. Changes the cast time and recast time based on the player's SpellReduction/WeaponskillReduction value.

**Parameter**

* (out) Spell : Spell - Spell object to compute the new timers of.

**Usage**

.. code-block:: python 

    newPlayer.computeActionTimer(Fire3)
