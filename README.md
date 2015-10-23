# Spring transaction in material design

Spring transaction explained with material design icons

## *PROPAGATION TYPE*

* *1st icon - when transaction exists*

* *2nd icon - when  none exists*

* *text description*

## MANDATORY
![support](https://raw.githubusercontent.com/google/material-design-icons/master/action/2x_web/ic_check_circle_black_48dp.png)
![exception](https://raw.githubusercontent.com/google/material-design-icons/master/alert/2x_web/ic_error_black_48dp.png)
Support a current transaction, throw an exception if none exists. Analogous to EJB.

## NEVER
![exception](https://raw.githubusercontent.com/google/material-design-icons/master/alert/2x_web/ic_error_black_48dp.png)
![no](https://raw.githubusercontent.com/google/material-design-icons/master/av/2x_web/ic_play_circle_filled_black_48dp.png)
Execute non-transactionally, throw an exception if a transaction exists. Analogous to EJB.


## SUPPORTS
![support](https://raw.githubusercontent.com/google/material-design-icons/master/action/2x_web/ic_check_circle_black_48dp.png)
![no](https://raw.githubusercontent.com/google/material-design-icons/master/av/2x_web/ic_play_circle_filled_black_48dp.png)
Support a current transaction, execute non-transactionally if none exists. Analogous to EJB.

## NOT SUPPORTED
![suspend](https://raw.githubusercontent.com/google/material-design-icons/master/av/2x_web/ic_pause_circle_filled_black_48dp.png)
![no](https://raw.githubusercontent.com/google/material-design-icons/master/av/2x_web/ic_play_circle_filled_black_48dp.png)
Execute non-transactionally, suspend the current transaction if one exists. Analogous to EJB.

## NESTED
![nested](https://raw.githubusercontent.com/google/material-design-icons/master/content/2x_web/ic_add_circle_black_48dp.png)
![create](https://raw.githubusercontent.com/google/material-design-icons/master/content/2x_web/ic_add_circle_black_48dp.png)
Execute within a nested transaction if a current transaction exists, behave like REQUIRED else. 
This transaction will be committed dependent from the outer transaction. There is no analogous feature in EJB.

## REQUIRED
![support](https://raw.githubusercontent.com/google/material-design-icons/master/action/2x_web/ic_check_circle_black_48dp.png)
![create](https://raw.githubusercontent.com/google/material-design-icons/master/content/2x_web/ic_add_circle_black_48dp.png)
Support a current transaction, create a new one if none exists. Analogous to EJB.

## REQUIRES NEW
![suspend](https://raw.githubusercontent.com/google/material-design-icons/master/av/2x_web/ic_pause_circle_filled_black_48dp.png)
![create](https://raw.githubusercontent.com/google/material-design-icons/master/content/2x_web/ic_add_circle_black_48dp.png)
Create a new transaction, and suspend the current transaction if one exists. This transaction will be committed or rolled back completely independent from the outer transaction. Analogous to the EJB.


# Transaction isolation

## READ UNCOMMITTED
![dr](http://uxrepo.com/static/icon-sets/google-material/png32/64/000000/android-brightness-1-64-000000.png)
![nrr](http://uxrepo.com/static/icon-sets/google-material/png32/64/000000/android-repeat-one-64-000000.png)
![pr](http://uxrepo.com/static/icon-sets/google-material/png32/64/000000/android-adb-64-000000.png)
A constant indicating that **dirty reads, non-repeatable reads and phantom reads** can occur. This level allows a row changed by one transaction to be read by another transaction before any changes in that row have been committed (a "dirty read"). If any of the changes are rolled back, the second transaction will have retrieved an invalid row.

## READ COMMITTED
![nrr](http://uxrepo.com/static/icon-sets/google-material/png32/64/000000/android-repeat-one-64-000000.png)
![pr](http://uxrepo.com/static/icon-sets/google-material/png32/64/000000/android-adb-64-000000.png)
A constant indicating that dirty reads are prevented; **non-repeatable reads and phantom reads** can occur. This level only prohibits a transaction from reading a row with uncommitted changes in it.

## REPEATABLE READ
![pr](http://uxrepo.com/static/icon-sets/google-material/png32/64/000000/android-adb-64-000000.png)
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
* [Android icons](http://uxrepo.com/tags/android)
