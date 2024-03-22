Player.updateCD()
=================

This function calls the two functions responsible for updating the cooldown of the player's different actions (one function for the role's actions and one of the job's actions).

**Parameter**

* time : float - Time by which to update by (in seconds).

**Usage**

.. code-block:: python

    Player.updateCD(0.01)

.. warning::

    Do not call this functions. It is being automatically called during simulation.