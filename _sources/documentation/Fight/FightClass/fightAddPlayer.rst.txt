Fight.AddPlayer()
=====================

This function adds the given player list to the fight's PlayerList list.

**Parameters**

playerList : list[Player] - List of player object to append.

**Usage**

.. code-block:: python

    # Usage
    BLMPlayer = Player([], [], BLMStat, JobEnum.BlackMage)
    RDMPlayer = Player([], [], RDMStat, JobEnum.RedMage)
    SMNPlayer = Player([], [], SMNStat, JobEnum.Summoner)
    playerList = [BLMPlayer, RDMPlayer, SMNPlayer]
    newFight.AddPlayer(playerList)