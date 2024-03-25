get_gearset_data()
==================

Gets the gear set data via an url (etro.gg).

**Parameter**

* set_id : str - Url/id of the etro.gg gear set.

**Return**

Returns a stat dictionnary corresponding to the given etro.gg gear set (dict[str : int]) or None if an error occured.

**Usage**

.. code-block:: python

    get_gearset_data("https://etro.gg/gearset/73f9f3af-2fa1-4871-85a3-a0f6adbb5e28")
    get_gearset_data("73f9f3af-2fa1-4871-85a3-a0f6adbb5e28") 
    # The two functions are equivalent.