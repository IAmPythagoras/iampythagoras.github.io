MitBuff.__init__()
==================

This is the constructor of the class MitBuff.

**Parameters**

* PercentMit : float -Percentage of the original damage taken once mitigation is applied. So if 30% mit, PercentMit = 0.7.
* Timer : float - Timer of the mit.
* Player : Player - Reference to the player on which this MitBuff is applied.
* MagicMit : bool - If the mitigation applies ONLY to magic damage.
* PhysicalMit : bool - If the mitigation applies ONLY to physical damage.
* BuffName : str - Name of the MitBuff.

.. warning::

    If the mitigation is applied both on magical and physical damage, MagicMit and PhysicalMit's value should be set to False. If they are
    both set to True an *InvalidMitigation* error will be raised.

.. warning::

    If the value of PercentMit is under 0 or above 1 an *InvalidMitigation* error will be raised.

**Usage**

.. code-block:: python

    newMitBuff = MitBuff(0.7, 15, Player(), MagicMit=False, PhysicalMit=False, BuffName="SussyBuff")