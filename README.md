# ACID in Practice

A simple banking system project developed in Python and SQLite to demonstrate the ACID properties in database transactions, including Atomicity, Consistency, Isolation, and Durability.

---

## Technologies Used

* Python
* SQLite
* Google Colab

---

## Project Objective

The objective of this project is to demonstrate how the ACID properties work in relational databases through practical examples using a simple banking system.

---

# ACID Properties Demonstrated

## Atomicity

A transfer transaction is canceled when an error occurs, ensuring that either the entire operation is completed or nothing is changed.

### Example

* Insufficient balance during a transfer
* Transaction canceled using `ROLLBACK`

---

## Consistency

The database enforces rules to prevent invalid data.

### Example

* Accounts cannot have negative balances
* Validation implemented using:

```sql
CHECK (saldo >= 0)
```

---

## Isolation

The project simulates concurrent transactions accessing the same balance, demonstrating how transaction isolation helps prevent conflicts and inconsistent data.

### Example

* Two transactions attempting to use the same balance simultaneously
* Validation before updating account balances

---

## Durability

After executing `COMMIT`, the changes are permanently stored in the database.

### Example

* Updated balances remain saved even after restarting the application

---

## Sample Table Structure

```sql
CREATE TABLE IF NOT EXISTS contas (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT NOT NULL,
    saldo REAL NOT NULL CHECK (saldo >= 0)
)
```

---

## Author
Daniela Schuck

Daniela Vaz
