Btxt - Base txt
A simple Python library for working with text-based databases.  
It allows you to create, modify, and manage structured text files  
using columns and rows, similar to a very basic table system.

Getting Started
1. Copy the file btxt.py into your project.
2. Import the class:

    from btxt import Btxt

3. Create a database object:

db = Btxt("my_database")

All operations will be performed on the file: my_database.txt


Main Methods
Database management:
- create_base()              Create an empty database file.
- delete_base()              Delete the database file.
- rename_base(new_name)      Rename the database file.
- duplicate_base()           Create a copy of the database (my_database1.txt, etc).
- clear()                    Clear all content of the database.

Column management:
- set_columns(*columns_name)     Define column headers.
- add_column(*new_column)        Add new columns to the database.
- del_columns(*columns_delete)   Remove selected columns.

Row and data management:
- add(*value)                Add a row to the database.
- count()                    Return the number of rows (excluding headers).
- find(*values)              Search for values in the database (prints matches).
- get_all()                  Print all rows from the database.


Example Usage
import random
from btxt import Btxt

# Create database
db = Btxt("Egg_metr_base")
db.create_base()

# Define columns
db.set_columns("ID", "height")

# Insert 100 rows
for i in range(100):
    db.add(str(random.randint(1, 10000)),
           f"{random.randint(150, 200)}cm")

# Count rows
print("Row count:", db.count())

# Search for a value
db.find("cm")

# Duplicate the database
db.duplicate_base()


Errors
Error 142 - Database not found during deletion
Error 143 - Database not found during rename
