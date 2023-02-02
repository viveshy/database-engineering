# Atomicity
- All queries in a transaction must succeed
- If one query fails, all prior successful quesries in transaction should rollback
- If the database went down prior to a commit of a transaction, all the successful queries in the transaction should rollback

Consider a scenario. We are transferring X amount from Account A to Account B. The amount gets debited from Account A and the system crashes. After we restarted the machine, Account A has been debited but Account B has not been credited. This is data loss and the information is inconsistent.

So, what does atomic transaction mean?
An atomic transaction is a transaction that will rollback all queries if one or more queries failed.

It is important to note that the lack of atomicity results in inconsistent information.

**P.S.** Database, after restart, should clean up the garbage created during crash.



