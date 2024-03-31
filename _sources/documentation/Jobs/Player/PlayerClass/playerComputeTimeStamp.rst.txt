Player.computeTimeStamp()
=========================

Computes an estimate of the player's final timestamp given its current ActionSet list.

**Return**

Returns a dictionnary {"currentTimeStamp" : timeStampEstimate(float), "untilNextGCD" : timeUntilNextGCDEstimate(float)}

**Usage**

.. code-block:: python

    newPlayer.computeTimeStamp()