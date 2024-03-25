findGCDTimerRange()
===================

Computes and returns all possible GCD timer given a min speed stat value, a max speed stat value and a haste value.

**Parameters**

* minSPDValue : int - Minimum speed stat value.
* maxSPDValue : int - Maximum speed stat value.
* subGCDHasteAmount : int - Haste amount to compute the sub GCD with. (Default 0)

**Returns**

It returns a dictionnary whos key is a tuple (gcdTimer, hastedGCDTimer) and it maps to one of the speed stat value that achieves those GCD timer. If subGCDHasteAmount if 0 then the key is (gcdTimer, gcdTimer). ie -> (2.42, 2.42) if subGCDHasteAmount is 0.

**Usage**

.. code-block:: python

        gcdTimerDict = findGCDTimerRange(400, 900,subGCDHasteAmount=15)