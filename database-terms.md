#### Isolation Level
* What the other transaction will see.
* The degree to which one transaction must be isolated from the resource or data modifications made by other transactions.
* The SQL standard defines four levels of transaction isolation: Read uncommitted, Read committed, Repeatable read and Serializable.
##### Dirty read
* Transaction may read data written but not yet committed by other transactions
* Transaction T1 modifies a row. Transaction T2 then reads that row before T1 performs a COMMIT. If T1 then performs a ROLLBACK, T2 will have read a row that was never committed and that may thus be considered to have never existed.
##### Non-repeatable read
*A transaction re-reads data it has previously read and finds that data has been modified by another transaction (that committed since the initial read).
* Transaction T1 reads a row. Transaction T2 then modifies or deletes that row and performs a COMMIT. If T1 then attempts to reread the row, it may receive the modified value or discover that the row has been deleted.
##### Phantom read
* A transaction re-executes a query returning a set of rows that satisfy a search condition and finds that the set of rows satisfying the condition has changed due to another recently-committed transaction.
* Transaction T1 reads the set of rows N that satisfy some `<search condition>`. Transaction T2 then executes SQL-statements that generate one or more rows that satisfy the `<search condition>` used by transaction T1. 
If transaction T1 then repeats the initial read with the same `<search condition>`, it obtains a different collection of rows.

| ISOLATION LEVEL  | Dirty read | Non-repeatable read | Phantom read| Description      |
| -------------    | -----------| -------------       | ------------| ------------
| READ UNCOMMITTED |    YES     |     YES             |    YES      |The transaction is allowed to read uncommitted changes to data.|
| READ COMMITTED   |    YES     |     YES             |    NO       |The transaction is allowed to read only committed changes to data.|
| REPEATABLE READ  |    NO      |     NO              |    YES      |The transaction can repeat the same query, and no rows that have been read by the transaction will have been updated or deleted.|
| SERIALIZABLE     |    NO      |     NO              |    NO       |No other transaction can modify the table. The transaction can repeat the same query, and receive exactly the same results. No rows can be inserted that would appear in the result set.|


#### Propagation
##### Required 
* Code will always run in a transaction. Creates a new transaction or reuses one if available.
##### Requires_new
* Code will always run in a new transaction. Suspends the current transaction if one exists.

