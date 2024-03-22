ImportGear()
============

This function imports a list of gear. It reads the given file and will output a dictionnary with each gear type as key with a list of all gear of that type in the import file.

The file itself must be a JSON format where the whole file is just a list. See examples on github.

**Parameter**

* fileName : str - Path of the file to read from.

**Return**

This function returns a dictionnary

**Usage**

.. code-block:: python

    gearSetDict = ImportGear("file.JSON")