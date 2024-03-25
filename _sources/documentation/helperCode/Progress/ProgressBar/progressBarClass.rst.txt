ProgressBar
===========

ProgressBar is the class responsble for generating and showing the progress bar.

.. note::

    A ProgressBar object should be initialized using the class method ProgressBar.init() which returns an iterator.

**Class attributes**

* ProgressBar.total : int - Total number of iterations the ProgressBar will go through (total number of steps).
* ProgressBar.currentProgress : int - Iteration step counter.
* ProgressBar.name : str - Name of the progress bar.
* ProgressBar.currentState : str - Last generated 'frame' of the progress bar.
* ProgressBar.extraBuffer : dictionnary to write the current progress bar frame onto (in the 'pb' key).
* ProgressBar.showBar : bool - If true prints the progress bar.
* ProgressBar.iterationAverage : float - Average time of one step.
* ProgressBar.sumIterations : float - Current total timer of the progress bar.
* ProgressBar.lastIterTime : float - Time of the last step.
* ProgressBar.lenLoadBar : int - Holds the current length of the string generated every frame.

**Class functions**

.. toctree::

    pbClassInit
    pbInit
    pbSetName
    pbSetShowBar
    pbSetExtraBuffer
    pbGetCurrentState
    pbIter
    pbNext
    pbComplete
    
    
