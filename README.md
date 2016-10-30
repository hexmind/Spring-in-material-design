# Spring transaction in pictures

## PROPAGATION TYPE

* 1st icon - when transaction exists

* 2nd icon - when none exists

## MANDATORY
![support](img/ic_check_circle_black_48dp.png)
![exception](img/ic_error_black_48dp.png)
Support a current transaction or throw an exception. Analogous to EJB.

## NEVER
![exception](img/ic_error_black_48dp.png)
![no](img/ic_play_circle_filled_black_48dp.png)
Throw an exception if a transaction exists or execute non-transactionally. Analogous to EJB.

## SUPPORTS
![support](img/ic_check_circle_black_48dp.png)
![no](img/ic_play_circle_filled_black_48dp.png)
Support a current transaction or execute non-transactionally. Analogous to EJB.

## NOT SUPPORTED
![suspend](img/ic_pause_circle_filled_black_48dp.png)
![no](img/ic_play_circle_filled_black_48dp.png)
Suspend the current transaction if one exists and execute non-transactionally. Analogous to EJB.

## NESTED
![nested](img/ic_add_circle_black_48dp.png)
![create](img/ic_add_circle_black_48dp.png)
Execute within a nested transaction if a current transaction exists, behave like REQUIRED else. 
Inner transaction will be committed dependent from the outer transaction. There is no analogous feature in EJB.

## REQUIRED
![support](img/ic_check_circle_black_48dp.png)
![create](img/ic_add_circle_black_48dp.png)
Support a current transaction or create a new one. Analogous to EJB.

## REQUIRES NEW
![suspend](img/ic_pause_circle_filled_black_48dp.png)
![create](img/ic_add_circle_black_48dp.png)
Suspend the current transaction if one exists and create a new one. This transaction will be committed or rolled back completely independent from the first transaction. Analogous to the EJB.


# Transaction isolation

## READ UNCOMMITTED
![dr](img/ic_pets.png)
![nrr](img/ic_repeat_one.png)
![pr](img/ic_person_outline_black_48dp.png)

A constant indicating that **dirty reads, non-repeatable reads and phantom reads** can occur. This level allows a row changed by one transaction to be read by another transaction before any changes in that row have been committed (a "dirty read"). If any of the changes are rolled back, the second transaction will have retrieved an invalid row.

## READ COMMITTED
![nrr](img/ic_repeat_one.png)
![pr](img/ic_person_outline_black_48dp.png)

A constant indicating that dirty reads are prevented; **non-repeatable reads and phantom reads** can occur. This level only prohibits a transaction from reading a row with uncommitted changes in it.

## REPEATABLE READ
![pr](img/ic_person_outline_black_48dp.png)

A constant indicating that dirty reads and non-repeatable reads are prevented; **phantom reads** can occur. This level prohibits a transaction from reading a row with uncommitted changes in it, and it also prohibits the situation where one transaction reads a row, a second transaction alters the row, and the first transaction rereads the row, getting different values the second time (a "non-repeatable read").

## SERIALIZABLE
A constant indicating that dirty reads, non-repeatable reads and phantom reads are prevented. This level includes the prohibitions in ISOLATION_REPEATABLE_READ and further prohibits the situation where one transaction reads all rows that satisfy a WHERE condition, a second transaction inserts a row that satisfies that WHERE condition, and the first transaction rereads for the same condition, retrieving the additional "phantom" row in the second read.


## More
### Spring
* [Propagation docs](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/transaction.html#tx-propagation)
* [Propagation enum](http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/transaction/annotation/Propagation.html)
* [Isolation enum](https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/transaction/annotation/Isolation.html)

### Material design
* [Guidelines](https://www.google.com/design/spec/material-design/introduction.html)
* [Materialup icons](http://www.materialup.com/tools/icons)