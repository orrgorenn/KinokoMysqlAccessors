# Kinoko MySQL Accessors

This repository provides MySQL-based accessor classes for integrating with the Kinoko server emulator, which originally utilizes CassandraDB. These accessors serve as a replacement for the original Cassandra-based accessors, facilitating interaction with MySQL databases.

## Features

- **MySQL Integration:** Seamlessly interact with MySQL databases using these accessor classes.
- **Kinoko Compatibility:** Designed to integrate with the Kinoko server emulator's architecture.
- **Comprehensive Accessors:** Includes classes for accounts, characters, friends, guilds, and more.

## Prerequisites

- **Java Development Kit (JDK):** Ensure JDK 21 is installed.
- **MySQL Server:** Install and configure MySQL Server.

## Setup Instructions

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/orrgorenn/KinokoMysqlAccessors.git
   cd KinokoMysqlAccessors
   ```

2. **Database Configuration:**

   - Create a MySQL database named `kinoko_mysql`.
   - Create a user `kinoko` with appropriate privileges.
   - Update the database connection details in your project's configuration to match your MySQL setup.

3. **Integrate Accessor Classes:**

   - Copy the accessor classes from this repository into your project's source directory.
   - Ensure your project recognizes these classes and that they are correctly referenced where needed.

4. **Modify Project Configuration:**

   - Update your project's database connection logic to utilize MySQL, referencing the new accessor classes.
   - Ensure all necessary MySQL drivers are included in your project's dependencies.

## Usage Example

```java
// Establish a connection to the MySQL database
Connection connection = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/kinoko_mysql", "kinoko", "your_password"
);

// Initialize the accessor
MysqlAccountAccessor accountAccessor = new MysqlAccountAccessor(connection);

// Retrieve account information
Account account = accountAccessor.getAccountById(1001);
System.out.println("Account Name: " + account.getName());
```

## Credits

These MySQL accessor classes are adapted from the original Cassandra-based accessors in the [Kinoko](https://github.com/iw2d/kinoko) project. All architectural credits go to the Kinoko development team.

## License

This project inherits the licensing terms of the original Kinoko repository. Please refer to the [Kinoko license](https://github.com/iw2d/kinoko/blob/main/LICENSE) for more details.

---

For contributions, suggestions, or issues, please open a pull request or an issue in this repository.

