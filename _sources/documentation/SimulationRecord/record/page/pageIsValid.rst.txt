page.isValid()
==============

Returns if the page fits the search requirements given.

**Parameters**

* startTime : float - Start time of the search query.
* endTime : float - End time of the search query.
* trackAutos : bool - If the query wants page that are autos.
* trackDOTS : bool - If the query wants page that are DOTS events.
* idList : list[int] - List of playerID to consider the events of.

**Return**

This function returns true if the page fits the requirements and false otherwise (boolean).

**Usage**

.. code-block:: python

    newPage.isValid(0,10,True, False, [1])