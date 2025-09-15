## 1. What is Polymorphism?

Polymorphism means **"many forms"**.\
In Object-Oriented Programming (OOP), it allows the same function,
method, or operator to behave differently depending on the object or
data type.

**Types in Python:** - Method Overriding (runtime polymorphism) - Method
Overloading (mimicked using default arguments or `*args`) - Operator
Overloading (e.g., redefining `+` for custom objects)

------------------------------------------------------------------------

## 2. What is Encapsulation in Python?

Encapsulation is the OOP concept of **wrapping data (variables) and
methods (functions)** inside a class and restricting direct access to
some components.\
In Python: - **Public members**: accessible everywhere. - **Protected
members** (`_var`): accessible but should not be accessed directly
outside class (convention). - **Private members** (`__var`):
name-mangled, not directly accessible.

It provides **data hiding** and **controlled access** using getters and
setters.

------------------------------------------------------------------------

## 3. What is RDBMS?

**RDBMS (Relational Database Management System)** is software that
stores and manages data in **tables (relations)**.\
Data is organized into rows and columns, and relationships between
tables are maintained using keys (Primary, Foreign).\
Examples: MySQL, PostgreSQL, Oracle, SQL Server.

------------------------------------------------------------------------

## 4. What is Normalization?

Normalization is the process of **organizing data in a database** to: -
Remove redundancy (duplicate data). - Improve data integrity.

**Normal Forms:** - 1NF: Atomic values, no repeating groups. - 2NF: No
partial dependency (applies if composite key exists). - 3NF: No
transitive dependency (non-key attributes depend only on primary key). -
BCNF: Stronger version of 3NF.

------------------------------------------------------------------------

## 5. What is Inheritance?

Inheritance is an OOP concept where one class (child) **acquires
properties and methods** of another class (parent).

**Types in Python:** - Single Inheritance - Multiple Inheritance -
Multilevel Inheritance - Hierarchical Inheritance - Hybrid Inheritance

Promotes **code reusability** and logical hierarchy.

------------------------------------------------------------------------

## 6. What is TCL in SQL?

**TCL (Transaction Control Language)** manages transactions in SQL.\
Commands: - **COMMIT**: Save changes permanently. - **ROLLBACK**: Undo
changes before commit. - **SAVEPOINT**: Set a point to roll back to. -
**SET TRANSACTION**: Define transaction properties.

TCL ensures **data consistency** and **safe execution** of database
operations.

------------------------------------------------------------------------

## 7. How to Change Owner in CLI?

In Linux/Unix CLI, you can use the `chown` command:

``` bash
chown user:group filename
```

-   `user`: new owner username
-   `group`: group name (optional)
-   `filename`: target file or directory

Example:

``` bash
chown prajjwal:developers project.py
```

This changes ownership of `project.py` to user `prajjwal` and group
`developers`.

------------------------------------------------------------------------
