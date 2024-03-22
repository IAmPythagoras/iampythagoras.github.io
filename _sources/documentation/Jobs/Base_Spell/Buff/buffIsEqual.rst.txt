buff.isEqual()
==============

This checks if two buffs are equal. Equality in this sense is defined as having the same value for all attributes of the buff class.

**Parameter**

* otherBuff : buff - Other buff to check equality for.

**Return**

This returns a boolean. True if they are equal false otherwise.

**Usage**

.. code-block:: python

    newBuff1 = buff(1.5, "sussy")
    newBuff2 = buff(1.1, "notsussy")
    newBuff3 = buff(1.1, "notsussy")

    newBuff1.isEqual(newBuff2) # Returns false
    newbuff1.isEqual(newBuff3) # Returns false
    newbuff2.isEqual(newBuff3) # Returns true