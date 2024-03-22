ActionEnum.name_for_id()
========================

This function returns the name of an action given an id. This function is a classmethod and so it must
be called on the class/subclass of ActionEnum itself.

**Parameter**

* id : int - Id of the action.

**Return**

This function returns a string. It either returns the name of the action (if it was found)
or returns 'Unknown' if it didn't find it.

**Usage**

.. code-block:: python

    BlackMageActions.name_for_id(152) # Should return FireIII
    BlackMageActions.name_for_id(99999) # Returns 'Unknown' since no action has this ID.
