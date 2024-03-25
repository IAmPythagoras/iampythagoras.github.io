ProgressBar.init()
==================

Class method which returns an iterator. Every time the iterator is iterated through it updates the progress bar.

**Parameters**

* total : int - Total number of iterations.
* name : str - Name of the progress bar.
* showBar : bool - If true will display the progress bar to the terminal when updating it. (Default true)
* extraBuffer : dict - Will write the most recent frame of the progress bar into the key 'pb' of that dictionnary. (Default None)

**Return**

This function returns an iterator object which will iterate 'total' step time and will update the progress bar every iterations.

**Usage**

.. code-block:: python

    newPb = ProgressBar.init(100, "NewPb")
    
    next(newPb) # Initializes pb
    for i in range(100):
        x = 1 # Will update ProgressBar every iterations.
        next(newPb) # Updates