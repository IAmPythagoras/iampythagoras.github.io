Player.__innit__()
==================


This is the constructor of the class Player.

**Parameters**

* ActionSet : list[Spell] - List of actions to perform. This attribute can be reassigned later. Can be left as an empty list here.
* EffectList : list[function] - List of all effect the player has at its creation. Can be left empty (and generally is).
* Stat : dict[str : int] - Stats of the player. The dictionnary given should always be of the form : *{'MainStat': 3378, 'WD': 132, 'Det': 1601, 'Ten': 400, 'SS': 824, 'SkS': 400, 'Crit': 2514, 'DH': 1402, 'Piety': 390}*.
* Job : JobEnum - Value of the job of the player (Ex: JobEnum.BlackMage, JobEnum.Scholar, JobEnum.Bard, JobEnum.Ninja,JobEnum.Warrior, etc.).

**Usage**

.. code-block:: python

    playerStat = {'MainStat': 3378, 'WD': 132, 'Det': 1601, 'Ten': 400, 'SS': 824, 'SkS': 400, 'Crit': 2514, 'DH': 1402, 'Piety': 390}
    blmPlayer = Player([], [], playerStat, JobEnum.BlackMage)