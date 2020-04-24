### Distributed Transactions
##### 2 Phase commit protocol
https://github.com/tzolov/narayana-jta-geode-support
* XA stands for extended architecture. It is one of implementation of 2PP.
* Parties involve are transaction manager and one or more resource managers.
* An example of a resource manager is a JDBC driver. 
* The transaction manager coordinates the transaction between the various resource managers.
* On a very broad level it consists of two steps.
* In the first step it polls all resource managers to check whether they are ready for committing the transaction. The resource manager may either reply with ready, not ready or read only. In the second phase the transaction manager tells all the resource managers to perform the actual commit or rollback.
* JTA transaction API specifies interfaces for distributed transactions. These interfaces specify the contract between the transaction manager and the resource manager, application or application server.
* There are many open-source and commercial, independent JTA transaction managers. In the open-source community, you have several choices like the Java Open Transaction Manager (JOTM), JBoss TS, Bitronix Transaction Manager (BTM), and Atomikos.
#### Pessimistic Locking
* Pessimistic locking assumes that concurrent transactions will `conflict` with each other, and requires resources to be locked after they are read and only unlocked after the application has finished using the data.

#### Optimistic Locking
* It deffer the `conflict` check until commit time. Optimistic locking assumes that multiple transactions can complete without affecting each other, and that therefore transactions can proceed without locking the data resources that they affect. Before committing, each transaction verifies that no other transaction has modified its data. If the check reveals conflicting modifications, the committing transaction rolls back.


#### Choreography

#### Orchestration