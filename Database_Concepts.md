
# Technical Paper on Fundamental Database Concepts

## Table of Contents
1. [ACID Properties](#acid-properties)  
2. [CAP Theorem](#cap-theorem)  
3. [Joins](#joins)  
4. [Aggregations and Filters in Queries](#aggregations-and-filters-in-queries)  
5. [Normalization](#normalization)  
6. [Indexes](#indexes)  
7. [Transactions](#transactions)  
8. [Locking Mechanism](#locking-mechanism)  
9. [Database Isolation Levels](#database-isolation-levels)  
10. [Triggers](#triggers)  

---

## ACID Properties
ACID is a set of properties that ensure reliable processing of database transactions.

1. **Atomicity**  
   - Ensures that a transaction is executed completely or not at all.  
   - Example: Money transfer — debit and credit must both succeed, or none should happen.

2. **Consistency**  
   - Guarantees that a transaction brings the database from one valid state to another.  
   - Example: A bank account balance cannot go negative if rules disallow it.

3. **Isolation**  
   - Transactions should not interfere with each other.  
   - Example: Two users booking the same flight seat must not see incorrect availability.

4. **Durability**  
   - Once committed, the results of a transaction remain even after a crash.  
   - Example: Once money is transferred, it remains in the account even after server failure.

---

## CAP Theorem
Proposed by Eric Brewer, CAP theorem applies to distributed databases.

- **Consistency (C):** Every read receives the most recent write.  
- **Availability (A):** Every request receives a response, even if some nodes fail.  
- **Partition Tolerance (P):** System continues to operate despite network partitions.  

**Theorem:** In any distributed system, only two out of the three guarantees can be achieved simultaneously.  

| Type | Guarantees | Examples |
|------|------------|----------|
| CP   | Consistency + Partition Tolerance | HBase, MongoDB (with strong consistency) |
| AP   | Availability + Partition Tolerance | Cassandra, DynamoDB |
| CA   | Consistency + Availability (rare in distributed systems) | Traditional RDBMS |

---

## Joins
Joins combine rows from multiple tables based on related columns.

1. **INNER JOIN** – Returns matching records in both tables.  
2. **LEFT JOIN** – Returns all rows from the left table and matching rows from the right.  
3. **RIGHT JOIN** – Returns all rows from the right table and matching rows from the left.  
4. **FULL OUTER JOIN** – Returns all rows when there is a match in either table.  
5. **CROSS JOIN** – Produces a Cartesian product.  

**Example:**
```sql
SELECT e.name, d.department_name
FROM Employees e
INNER JOIN Departments d
ON e.department_id = d.id;
```

---

## Aggregations and Filters in Queries
Aggregations summarize data, while filters narrow results.

- **Aggregations**: `SUM()`, `AVG()`, `COUNT()`, `MIN()`, `MAX()`.  
- **Filters**: `WHERE`, `HAVING`.  

**Example:**
```sql
SELECT department_id, COUNT(*) AS total_employees, AVG(salary) AS avg_salary
FROM Employees
WHERE salary > 50000
GROUP BY department_id
HAVING COUNT(*) > 5;
```

---

## Normalization
Normalization reduces redundancy and ensures data integrity.

1. **1NF (First Normal Form):** Eliminate repeating groups, atomic values only.  
2. **2NF:** Meet 1NF + remove partial dependencies.  
3. **3NF:** Meet 2NF + remove transitive dependencies.  
4. **BCNF:** A stronger version of 3NF.  

**Example:**  
- Without normalization: Employee table contains multiple phone numbers in one column.  
- With 1NF: Separate into `Employee` and `Phone` tables.

---

## Indexes
Indexes improve query performance by enabling faster data retrieval.

- **Clustered Index:** Sorts and stores rows in order. (One per table).  
- **Non-Clustered Index:** Creates a separate structure pointing to the data.  
- **Composite Index:** Uses multiple columns.  

**Trade-off:** Indexes speed up `SELECT` but slow down `INSERT`/`UPDATE` due to maintenance.

---

## Transactions
A **transaction** is a sequence of operations executed as a single logical unit.

- Begin with `START TRANSACTION` or `BEGIN`.  
- Commit with `COMMIT`.  
- Rollback with `ROLLBACK`.  

**Example:**
```sql
START TRANSACTION;
UPDATE Accounts SET balance = balance - 1000 WHERE id = 1;
UPDATE Accounts SET balance = balance + 1000 WHERE id = 2;
COMMIT;
```

---

## Locking Mechanism
Locks ensure consistency when multiple users access the same data.

1. **Shared Lock (Read Lock):** Multiple users can read, but not write.  
2. **Exclusive Lock (Write Lock):** Only one transaction can read/write.  
3. **Row-level Lock:** Locks a specific row.  
4. **Table-level Lock:** Locks the entire table.  

**Deadlocks:** Occur when two transactions wait for each other’s locks.

---

## Database Isolation Levels
Isolation levels control how transaction integrity is maintained.

| Level | Phenomena Prevented | Issues |
|-------|----------------------|--------|
| Read Uncommitted | None | Dirty Reads |
| Read Committed | Dirty Reads | Non-repeatable Reads |
| Repeatable Read | Dirty, Non-repeatable Reads | Phantom Reads |
| Serializable | All | Slow performance |

**Example (MySQL):**
```sql
SET TRANSACTION ISOLATION LEVEL REPEATABLE READ;
```

---

## Triggers
Triggers are procedures that execute automatically in response to database events.

- **BEFORE Trigger:** Executes before an insert, update, or delete.  
- **AFTER Trigger:** Executes after an insert, update, or delete.  
- **INSTEAD OF Trigger:** Used in views.  

**Example:**
```sql
CREATE TRIGGER before_insert_employee
BEFORE INSERT ON Employees
FOR EACH ROW
SET NEW.created_at = NOW();
```

---

## Conclusion
Understanding these core database concepts is essential for designing efficient, consistent, and scalable applications. Together, they provide the foundation for ensuring data reliability, performance optimization, and integrity in modern database systems.
