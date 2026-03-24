# SQLite CLI Quick Reference

## Exporting Query to CSV

```bash
# Basic CSV export
sqlite3 database.db "SELECT * FROM table_name;" > output.csv

# With headers
sqlite3 -header -csv database.db "SELECT * FROM table_name;" > output.csv

# Multi-line query
sqlite3 -header -csv database.db <<EOF > output.csv
SELECT column1, column2, column3
FROM table_name
WHERE condition = 'value'
ORDER BY column1;
EOF
```

## Opening a Database

```bash
# Open existing database
sqlite3 database.db

# Create new database
sqlite3 new_database.db
```

## Basic Commands Inside SQLite CLI

```sql
-- List all tables
.tables

-- Show table schema
.schema table_name

-- Show all schemas
.schema

-- Enable headers and column mode
.headers on
.mode column

-- Import CSV into table
.mode csv
.import data.csv table_name

-- Export table to CSV
.headers on
.mode csv
.output output.csv
SELECT * FROM table_name;
.output stdout

-- Show current settings
.show

-- Execute SQL file
.read script.sql

-- Exit SQLite
.quit
-- or
.exit
```

## Common Query Operations

```sql
-- View data
SELECT * FROM table_name LIMIT 10;

-- Count rows
SELECT COUNT(*) FROM table_name;

-- Filter data
SELECT * FROM table_name WHERE column = 'value';

-- Join tables
SELECT * FROM table1 
JOIN table2 ON table1.id = table2.table1_id;
```

## Database Information

```sql
-- List all databases
.databases

-- Show current database file
.database

-- Database integrity check
PRAGMA integrity_check;

-- Table info
PRAGMA table_info(table_name);
```

## Useful Flags

```bash
# Execute command and exit
sqlite3 database.db "SELECT COUNT(*) FROM table_name;"

# Read-only mode
sqlite3 -readonly database.db

# Show execution time
sqlite3 database.db ".timer on" "SELECT * FROM large_table;"

# Verbose output
sqlite3 -echo database.db < script.sql
```

## Tips

- Commands starting with `.` are SQLite meta-commands (not SQL)
- SQL statements must end with `;`
- Use `.help` to see all available commands
- Use `.help COMMAND` for specific command help
- Press Ctrl+D (Unix) or Ctrl+Z (Windows) to exit
