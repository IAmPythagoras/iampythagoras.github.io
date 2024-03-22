PlayerEnum.id_for_name()
========================

This function returns the id of a Role/Job given a name. This function is a classmethod and so it must
be called on the class/subclass of PlayerEnum itself.

**Parameter**

* name : string - Name of the Role/job.

**Return**

This function returns the id (int) of the Role/Job or returns (-1) if the Role/Job was not found.

**Usage**

.. code-block:: python

    JobEnum.id_for_name("BlackMage") # Should return 1
    RoleEnum.id_for_name("PhysicalRanged") # Should return 5

