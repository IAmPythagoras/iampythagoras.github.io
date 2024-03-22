Gear
====

Gear is an object that represents a gear piece.

**Class attributes**

* Gear.GearType : GearType - Type of the gear.
* Gear.Stat : Dict[str : int] - Dictionnary mapping the different stat name to their value for this gear piece.
* Gear.Name : str - Name of the gear.
* Gear.StatLimit : int - Max limit that the gear piece can have of one stat. (Equal to the value of its strongest stat).
* Gear.illegalMeld : bool - True if the gear piece has any illegal melds.
* Gear.__ignoreOptimize : bool - This is to tell the solver to not optimize the melds of this gear piece. Private attribute.
* Gear.weaponDelay : float - Weapon delay value. Only relevant for weapon.
* Gear.Materias : list[Materia] - List of all materia object on that gear piece.
* Gear.MateriaLimit : int - Max number of materia this gear piece can receive (legally).
* Gear.MateriasCount : int - Counter of the current number of materias on that gear piece.

**Class functions**

.. toctree::

    gearInit 
    gearGetStat
    gearAddMateria
    gearGetMateriaNumber
    gearGetWeaponDelay
    gearGetNumberPossibleMateria
    gearGetGearTypeName
    gearGetMateriaTypeList
    gearGetNumberMateria
    gearSetWeaponDelay
    gearSetIgnoreOptimize
    gearGetIgnoreOptimize
    gearSetStatLimit
    gearForceAddMateria
    gearHasValidMelding
    gearCanAddMateriaNoLoss
    gearCanReplaceMateriaNoLoss
    gearHasMateriaType
    gearResetMateriaSlot
    gearRemoveMateriaType
    gearStr
    gearHasStatType
    gearAddMateriaPrivate