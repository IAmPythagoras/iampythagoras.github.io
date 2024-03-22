ActionEnum.id_for_name()
========================

This function returns the id of an action given a name. This function is a classmethod and so it must
be called on the class/subclass of ActionEnum itself.

**Parameter**

* name : string - Name of the action.

**Return**

This function returns the id (int) of the action or returns (-1) if the action was not found.

**Usage**

.. code-block:: python

    BlackMageActions.id_for_name("FireIII") # Should return 152
    BlackMageActions.id_for_name("FireV") # Should return -1 as FireV does not exist (yet right?)

