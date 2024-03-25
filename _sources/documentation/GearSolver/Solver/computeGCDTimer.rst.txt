computeGCDTimer()
=================

Computes and returns the value of the GCD timer with and without haste given a speed stat (from the stat) value and a haste value.

**Parameters**

* speedStatValue : int - Speed stat value from a stat dictionnary (not f_SPD).
* subGCDHasteAmount : int - Haste amount to compute the hasted GCD timer with.

**Returns**

This function returns the GCD timer of the given speed stat with and without haste as a tuple of string : (gcdTimer, gcdTimerWithHaste) (str, str).

**Usage**

.. code-block:: python

    computeGCDTimer(1900, 20)