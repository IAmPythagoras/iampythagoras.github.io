DOTSpell.__init__()
===================

This is the constructor of the class DOTSpell.

**Parameter**

* id : int - Unique identifier of the DOT.
* Potency : int - Base potency of the DOT.
* isPhysical : bool - True if the DOT does physical damage. False otherwise.
* isGround : bool - True if the DOT comes from a ground AOE. (Default True)

**Usage**

.. code-block:: python

    newDOT = DOTSpell(1, 100, False, isGround=True)