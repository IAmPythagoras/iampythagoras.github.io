Fight 
=====

Fight is the object representating an instance of a simulation. It orchestrates all the other classes so the simulation happens.

**Class attributes**

* Fight.TimeStamp : float - Timestamp in seconds of the simulation.
* Fight.TeamCompositionBonus : float - Percent bonus to players' main stat due to team composition. This value is computed as the simulation starts.
* Fight.FirstHit : bool - Is set to true on the first instance of damage in the simulation.
* Fight.RequirementOn : bool - If is true the simulation will ignore any failed requirements.
* Fight.FightStart : bool - Is set to true when the fight starts.
* Fight.IgnoreMana : bool - If set to true the simulator will ignore any failed requirements due mana.
* Fight.timeValue : list[float] = List that holds all the individual time the simulator will sample DPS to make the graph.
* Fight.failedRequirementList : list[failedRequirementEvent] = List that holds all *failedRequirementEvent* objects of the simulation.
* Fight.waitingThreshold : float - Maximum amount of time a player can wait if an action is on cooldown before it is declared a failed requirement (default to 1).
* Fight.wipe : bool - Set to true if party wipes due to damage or failed requirements during the simulation.
* Fight.PlayerList : list[Player] = List that contains all the *Player* object of the simulation.
* Fight.MaxPotencyPlentifulHarvest : bool - If true any plentiful harvest done by a reaper will have maximum potency.
* Fight.TimeUnit : float - The amount of time the simulation will increase the timestamp by each frame.
* Fight.nextID : int -Value to give to the next added player's id.
* Fight.simulationRecord : SimulationRecord = Reference to the *SimulationRecord* object. By default is a newly created *SimulationRecord*.
* Fight.SavePreBakedAction : bool - If set to true the simulation will save the needed actions into *PreBakedActions*.
* Fight.PlayerIDSavePreBakedAction : int -ID of the player to save actions into *PreBakedActions*.
* Fight.alwaysAllowConditionalAction : bool - If true any conditional action will always succeed its condition.

**Class functions**

.. toctree::
    
    fightInnit
    fightAddPlayer
    fightGetPlayerPrepullLength
    fightSyncPlayerPrePull
    fightSimulateFight
    fightComputeFunctions
    fightDeepCopy
    fightGetEnemityList
    fightPlayerForID
    fightSimulatePreBakedFight
    fightSimulateZIPFight