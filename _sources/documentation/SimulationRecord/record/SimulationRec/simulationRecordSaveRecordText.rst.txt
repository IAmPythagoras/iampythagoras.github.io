SimulationRecord.saveRecordText()
=================================

This function saves the simulation record as a text file. It converts the SimulationRecord object to a string (using SimulationRecord.__str__()) and saves the string to a file. It also allows to filter out some of the pages.

**Parameters**

* idList : list[int] - List of player ids to consider pages of when exporting. If left empty does not filter by player id.
* path : str - Path and name of the file to save to. (Relative path).
* startTime : float - Start time to filter by. (Default 0)
* endTime : float - End time to filter by. (Default 99999)
* trackAutos : bool - If true the exported record will have pages that are autos. If false these are not included. (Default true)
* trackDOTs : bool - IF true the exported record will have pages that are DOTs. If false these are not included. (Default true) 
* customizeRecord : bool - If false no attempt at filtering the exported pages will be done. (Default false)

**Return**

This function doesn't return anything, but it saves the file.

**Usage**

.. code-block:: python

    newSimRec.saveRecordText([], "SimulationRecord.txt")
    # Does not filter any pages.