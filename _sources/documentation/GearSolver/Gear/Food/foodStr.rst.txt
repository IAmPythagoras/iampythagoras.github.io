Food.__str__()
==============

This function is the string casting of a Food object.

**Return**

This function returns a string of the format : 'Food.name gives : StatName % max of MAX | ... '.


**Usage**

.. code-block:: python

    HD = Food({"DH" : [103, 0.1], "Det" : [62, 0.1]}, "Honeyed Dragonfruit")
    print(HD)  
    # prints out : Food Honeyed Dragonfruit gives -> DH 10% max of 103 |Det 10% max of 62 |