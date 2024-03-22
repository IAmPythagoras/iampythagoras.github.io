GearSet.__str__()
=================

This is the casting of the GearSet object into string.

**Return**

THis function returns a string.

**Usage**

.. code-block:: python

    print(newGearSet)
    #	WEAPON : Crit : 306 | SS : 214 | MainStat : 416 | WD : 132 |  Materias : SS : 36 | SS : 36 |  Name : Raid
    #	HEAD : SS : 184 | Det : 129 | MainStat : 248 |  Materias : DH : 36 | DH : 36 |  Name : Raid
    #	BODY : SS : 292 | DH : 204 | MainStat : 394 |  Materias : Det : 36 | Det : 36 |  Name : Raid
    #	HANDS : SS : 184 | DH : 129 | MainStat : 248 |  Materias : Det : 36 | Det : 36 |  Name : Tome
    #	LEGS : Det : 292 | SS : 204 | MainStat : 394 |  Materias : SS : 36 | SS : 36 |  Name : Tome
    #	FEET : Det : 184 | SS : 129 | MainStat : 248 |  Materias : DH : 36 | SS : 36 |  Name : Raid
    #	EARRINGS : DH : 102 | SS : 145 | MainStat : 196 |  Materias : Det : 36 | Det : 36 |  Name : Tome
    #	NECKLACE : SS : 102 | DH : 145 | MainStat : 196 |  Materias : Det : 36 | SS : 36 |  Name : Raid
    #	BRACELETS : Det : 145 | SS : 102 | MainStat : 196 |  Materias : DH : 36 | SS : 36 |  Name : Tome
    #	LRING : Det : 102 | Crit : 145 | MainStat : 196 |  Materias : SS : 36 | SS : 36 |  Name : Raid
    #	RING : SS : 102 | DH : 145 | MainStat : 196 |  Materias : Det : 36 | SS : 36 |  Name : Raid
    #	Final Stats : {'MainStat': 3378, 'WD': 132, 'Det': 1530, 'Ten': 400, 'SS': 2521, 'SkS': 400, 'Crit': 851, 'DH': 1331, 'Piety': 390}
    #	Materia numbers : SS 10x |DH 4x |Det 8x |
    #	Food Caviar Sandwich gives -> SS 10% max of 103 |DH 10% max of 62 |