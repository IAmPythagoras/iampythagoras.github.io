testImplementation
==================

testImplementation is the module responsible for the testing of code. It holds the class 'test' and 'testsuite' and all the other tests to execute.

If you wish to see more about how the individual tests are implemented please go check the page on github.

You can launch all currently implemented test suites using 

.. code-block:: text

    python -m ffxivcalc -vvv tests

This will launch all testsuites and export the results in a log file.

**Import**

.. code-block:: python

    from ffxivcalc.Tester.testImplementation import test, testsuite

.. toctree::

    test/testClass
    testSuite/testSuiteClass