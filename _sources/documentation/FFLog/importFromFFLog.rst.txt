Import fight from FFLogs
========================

To import a fight from FFLogs you can use the *getSingleFightData()* function.

.. note::

    You can obtain a client Id and client secret here : https://www.fflogs.com/api/clients/.

**getSingleFightData()**

This function returns a dictionnary that corresponds to the fight from FFLogs (saved in a format ffxivcalc can understand).

**Function Parameters**

* clientId : str - Your client ID from the FFLog api.
* clientSecret : str - Your client secret from the FFLog api.
* code : str - Record code.
* id : str - Fight id (in the record).
* showProgress : bool - If true shows progress (default false).
* max_time : float - Max timestamp to import. If let as 0 will import the whole fight (default 0).

**Return**

This function returns a dictionnary corresponding to a format ffxivcalc can understand. You can then use the *RestoreFightObject* function on that dictionnary to get a Fight object that you can simulate.

**Usage**

.. code-block:: python

    from ffxivcalc.helperCode.helper_backend import RestoreFightObject
    from ffxivcalc.Request.FFLogs_api import getSingleFightData

    data = getSingleFightData("YOUR ID", "YOUR SECRET", "YbDaH9C6dNVJAh8T",
                              "67", showProgress=True, max_time=50)
    RestoreFightObject(data)