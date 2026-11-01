# Student Finance Manager

A Java Swing desktop app for recording income and expenses in MongoDB.

![Java](https://img.shields.io/badge/Java_17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Swing](https://img.shields.io/badge/Swing-5382A1?style=for-the-badge&logo=openjdk&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)

## About

Despite the repository name, the code here is a small personal finance tracker for students rather than a to-do app. A Swing form lets you enter a transaction (description, amount, income or expense, date), save it to a local MongoDB database, and view every saved transaction in a table.

## Features

- Swing form with description, amount, type (`income` / `expense`) and date fields
- **Save Transaction** inserts the entry into the `transactions` collection of the `FinanceDB` database
- **View Transactions** opens a window with all transactions in a `JTable`
- A console entry point (`App`) that saves a sample transaction and prints all transactions

## Tech Stack

- Java 17, Swing
- MongoDB Java sync driver 4.11
- Maven, JUnit 3

## Project Structure

```
FinanceManager/
├── pom.xml
└── src/
    ├── main/java/com/student/finance/
    │   ├── FinanceManagerUI.java      # Swing UI (main entry point)
    │   ├── App.java                   # Console demo
    │   ├── Transaction.java           # Model
    │   ├── TransactionDAO.java        # Save / fetch from MongoDB
    │   ├── TransactionTableModel.java # JTable model
    │   └── MongoDBUtil.java           # Connection to mongodb://localhost:27017
    └── test/java/com/student/finance/AppTest.java
```

## Getting Started

Prerequisites: JDK 17, Maven, and MongoDB running on `localhost:27017`.

```bash
cd FinanceManager
mvn compile

# Run the Swing app
mvn exec:java -Dexec.mainClass=com.student.finance.FinanceManagerUI
```

The `exec` plugin is not declared in `pom.xml`, so Maven resolves it on first use. You can also run `FinanceManagerUI` (or `App` for the console demo) directly from your IDE.

## Author

**Aryan Bhandari**: [GitHub](https://github.com/aryanbha123)
