test.__init__()
===============

This is the constructor of the test class.

**Parameters**

* testName : str - Name of the test.
* testFunction : function -> T - Test function (holds the code to test).
* validationFunction : function(T) -> bool - Validating function of the test.

**Usage**

.. code-block:: python

    def testFunc():
        x = 1
        return x

    def validFunc(testResult):
        return testResult == 1

    newTest = test('isX1', testFunc, validFunc)
    # This test is to test weither x will in fact be 1 in the code above.