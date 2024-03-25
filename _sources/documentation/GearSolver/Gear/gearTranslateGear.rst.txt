translateGear()
===============

This function takes a list of gear and returns a dictionnary with each gear in a key corresponding to their type.

This function is used by ImportGear().

**Parameter**

* data : list[dict] - This is a list of dictionnary entries that correspond to gear.

**Return**

This function returns a dictionnary where the keys are the GearType's value (in string) and it maps to a list of all the gear objects
created from the given data. (dict[str : list[Gear]])

**Usage**

.. code-block:: python

    def ImportGear(fileName : str) -> dict:

        GearDict = {}
        try:
            f = open(fileName) #Opening save
            GearDict = translateGear(json.load(f))
        except:
            raise InvalidFileName(fileName)

        return GearDict