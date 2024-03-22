PlayerEnum.name_for_id()
========================

This function returns the name of a Role/Job given an id. This function is a classmethod and so it must
be called on the class/subclass of PlayerEnum itself.

**Parameter**

* id : int - Id of the Role/Job.

**Return**

This function returns a string. It either returns the name of the Role/Job (if it was found)
or returns 'Unknown' if it didn't find it.

**Usage**

.. code-block:: python

    RoleEnum.name_for_id(1) # Should return Caster
    RoleEnum.name_for_id(99999) # Returns 'Unknown' since no Role/Job has this ID.
