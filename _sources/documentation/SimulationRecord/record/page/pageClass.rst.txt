page
====

A page corresponds to one individual event and its information. A record has a list of pages that each correspond to one damage event of the fight.

**Class attributes**

* page.Name : str - Name of the page. Can be left as 'Unnamed'.
* page.Potency : int - Potency of the event the page is recording.
* page.Damage : int - Damage of the event the page is recording.
* page.TimeStamp : float - Timestamp of the event the page is recording.
* page.autoCrit : bool - True if the event the page is recording was an auto critical hit.
* page.autoDH : bool -  True if the event the page is recording was an auto direct hit.
* page.PercentBuffList : list[buff] - List of all buff object on the event the page is recording.
* page.DHBuffList : list[(str, int)] - List of all direct hit buff increase on the event the page is recording. The tuple it holds is (buffName, buffPercentIncrease).
* page.CritBuffList : list[(str, int)] - List of all critical hit buff increase on the event the page is recording. The tuple it holds is (buffName, buffPercentIncrease).
* page.playerID : int - ID of the player of the event the page is recording.
* page.hasPotion : bool - True if the event the page is recording is buffed by a potion effect.
* page.isAuto : bool - True if the event the page is recording is an auto attack.
* page.isDOT : bool - True if the event the page is recording is a DOT.

**Class functions**

.. toctree::

    pageInit
    pageSetPlayerID
    pageSetName
    pageSetPotency
    pageSetDamage
    pageSetTimeStamp
    pageSetAutoCrit
    pageSetAutoDH
    pageAddPercentBuff
    pageAddDHBuffList
    pageAddCritBuffList
    pageSetHasPotion
    pageSetIsDOT
    pageSetIsAuto
    pageIsValid
    pageStr
