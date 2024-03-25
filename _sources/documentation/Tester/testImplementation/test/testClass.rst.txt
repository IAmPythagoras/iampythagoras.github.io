test
====

test is a class that represents one test case.

**Class parameters**

* test.testName : str - Name of the test.
* test.testFunction : function - Function to execute when testing. This contains the code that we want to test.
* test.validationFunction : function - Function to execute to validate the result of the test. This functions checks the output of test.testFunction and returns true if the test was successful.

**Class functions**

.. toctree::

    testInit    
    testExecuteTest 


