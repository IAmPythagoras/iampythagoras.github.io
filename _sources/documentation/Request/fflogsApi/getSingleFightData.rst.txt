getSingleFightData()
====================

Gets a fight data from fflog and returns the data corresponding to that fight in a format ffxivcalc can use.

**Parameters**

* clientId : str - Your client Id from fflogs. If left empty doesn't write to environ.
* clientSecret : str - Your client secret from fflogs. If left empty doesn't write to environ.
* code : str - Code of the fights record.
* id : str - Id of the fight.
* showProgress : bool = False - If true a progress bar will be shown.
* max_time : float = 0 - Max time stamp to take from fflogs. If left as default (0) it does not limit time stamp.

**Return**

This function returns a dictionnary that corresponds to a saved file ffxivcalc can understand.

**Usage**

.. code-block:: python

    from ffxivcalc.helperCode.helper_backend import RestoreFightObject

    data = getSingleFightData("YOUR CLIENT", "YOUR SECRET", "YbDaH9C6dNVJAh8T", "67", showProgress=True)
    fight = RestoreFightObject(data) # Restores the saved json format as a fight object.