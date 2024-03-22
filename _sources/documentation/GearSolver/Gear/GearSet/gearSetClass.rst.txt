GearSet 
=======

GearSet is a class that represents a whole gear set. It is made of a certain food and a certain amount of Gear objects.

**Class attributes**

* GearSet.GearSet : dict[str : Gear] - Dictionnary that maps the name of a gear piece to the gear piece object.
* GearSet.Food : Food - Food object associted to the gear set.
* GearSet.gearSetIter : iter - Iterator of GearSet.GearSet dictionnary.

**Class functions**

.. toctree::

    gearSetInit
    gearSetIter
    gearSetNext
    gearSetRemoveMateriaType
    gearSetRemoveFirstFoundMateriaInvalidPiece
    gearSetRemoveMateriaSpecGear
    gearSetAddFood
    gearSetRemoveFood
    gearSetStr 
    gearSetFindFirstPieceMateria
    gearSetAddGear
    gearSetStrMateriaNumber
    gearSetRemoveGear 
    gearSetGetMateriaLimit
    gearSetGetMateriaTypeLimit
    gearSetGetNumberMateria
    gearSetResetGearSet
    gearSetGetWeaponDelay
    gearSetGetGearSetStat
    gearSetHasValidMelding
    gearSetGetMateriaTypeList