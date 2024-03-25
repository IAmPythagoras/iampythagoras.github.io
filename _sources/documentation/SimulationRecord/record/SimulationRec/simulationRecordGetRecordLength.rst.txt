SimulationRecord.getRecordLength()
==================================

Returns the length (number of pages) of the record given some restrictions.

* startTime : float - Start time to filter by.
* endTime : float - End time to filter by.
* trackAutos : bool - If true will allow pages that are autos.
* trackDOTs : bool - If true will allow pages that are DOT.
* idList : list[int] - List of playerID to consider. If left empty no filtering is done on the page.playerID.

**Return**

This function returns the number of pages in that SimulationRecord that fits the given requirements (int).

**Usage**

.. code-block:: python

    nPages = newSimRec.getRecordLength(10,50, True, False, [])