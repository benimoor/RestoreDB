# RestoreDB# Database Restore Scripts

These bash scripts simplify the process of restoring databases in MySQL and PostgreSQL. They support creating users and databases, granting necessary privileges, and restoring from SQL files.

## Features

- **User and Database Creation**: Automatically creates the required user and database.
- **Database Restoration**: Restores the database from an SQL file.
- **Environment Support**: Works with both MySQL and PostgreSQL.
- **Security**: Handles passwords securely and minimizes privilege escalation.

---

## Scripts Overview

### 1. PostgreSQL Restore Script
**File:** `createpsql`

This script supports creating a PostgreSQL user and database, granting privileges, and restoring from an SQL file.

#### Usage
```bash
./createpsql {mode} {username} {db_name} {password} [optional_sql_file_path]
```

#### Modes
- **create**: Creates the user and database, then optionally restores from an SQL file.
- **restore**: Skips user and database creation and only restores from the SQL file.

#### Example
```bash
# Create user and database, then restore
./createpsql create myuser mydb mypass /path/to/file.sql

# Only restore an existing database
./createpsql restore myuser mydb mypass /path/to/file.sql
```

#### Notes
- Prompts for the PostgreSQL admin password.
- Temporarily grants `SUPERUSER` role to facilitate restoration.

---

### 2. MySQL Restore Script
**File:** `createmysql`

This script supports creating a MySQL user and database, granting privileges, and restoring from an SQL file.

#### Usage
```bash
./createmysql {mode} {username} {db_name} {password} [optional_sql_file_path]
```

#### Modes
- **create**: Creates the user and database, then optionally restores from an SQL file.
- **restore**: Skips user and database creation and only restores from the SQL file.

#### Example
```bash
# Create user and database, then restore
./createmysql create myuser mydb mypass /path/to/file.sql

# Only restore an existing database
./createmysql restore myuser mydb mypass /path/to/file.sql
```

#### Notes
- Requires `sudo` privileges to interact with MySQL.

---

## Requirements

### PostgreSQL
- PostgreSQL installed and configured.
- `psql` command-line tool available.

### MySQL
- MySQL installed and configured.
- `mysql` command-line tool available.
- Requires `sudo` privileges.

---

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/benimoor/RestoreDB.git
   ```
2. Navigate to the directory:
   ```bash
   cd RestoreDB
   ```
3. Make the scripts executable:
   ```bash
   chmod +x createmysql createpsql
   ```

---

## Contribution
Feel free to open issues or submit pull requests for any improvements or bug fixes.

---