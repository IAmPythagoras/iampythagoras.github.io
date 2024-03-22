PreBakedAction.resetPercentageBonus()
=====================================

This function resets the PercentageBonus of a PreBakedAction. This action is required after using a Fight.SimulatePreBakedFight() as this function
modifies and appends required buffs to the PreBakedAction.PercentageBonus list. If the list was not resetted buffs would transfer to the next simulation as well.

**Usage**

.. code-block:: python

    newPreBakedAction.resetPercentageBonus()