SimulationRecord.saveRecord()
=============================

Exports the simulation record as a PDF file that shows all pages that passed filtering.

* customizeRecord : bool - If false no attempt at filtering the exported pages will be done. (Default false)
* path : str - Path and name of the file to save to. (Relative path).
* startTime : float - Start time to filter by. (Default 0)
* endTime : float - End time to filter by. (Default 99999)
* trackAutos : bool - If true the exported record will have pages that are autos. If false these are not included. (Default true)
* trackDOTs : bool - IF true the exported record will have pages that are DOTs. If false these are not included. (Default true) 
* idList : list[int] - List of player ids to consider pages of when exporting. If left empty does not filter by player id. (Default [])
* saveAsPDF : bool - If true the function will save the matplotlib figure as a pdf file. (Default true)

**Returns**

Returns the figure object (matplotlib) created and saves the file if saveAsPDF is true as 'SimulationRecord.pdf'.

**Usage**

.. code-block:: python

    newSimRec.saveRecord() # No filtering is done.