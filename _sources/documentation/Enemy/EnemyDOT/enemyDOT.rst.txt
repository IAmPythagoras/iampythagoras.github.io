EnemyDOT
========

This class represents any DOT (Damage over time) applied on Players resulting from an EnemyEvent done by an Enemy object.

**Class attributes**

* EnemyDOT.id : int - Unique identifier of the DOT.
* EnemyDOT.DOTDamage : int - Damage done every tic of the DOT.
* EnemyDOT.DOTDuration : float - Duration of the DOT.
* EnemyDOT.DOTStateTimer : float - Current timer of the DOT (timer before next tic).

**Class functions**

.. toctree::
    enemyDOTInnit
    enemyDOTUpdateState