# PandasDB

PandasDB is a lightweight wrapper library that combines the power of SQLite databases with the ease of use of Python numerical libraries like pandas, numpy, scipy, etc. This library allows you to store and manage data using a modern SQLite database, while still being able to use query results seamlessly in python.

## Why bother with PandasDB?

### Features
- Fast and reliable data storage and management.
- Easy to use, with no setup required.
- Designed for use in Jupyter notebooks.
- Easily import data from different file formats.
- Leverage powerful SQL syntax for advanced data manipulation and analysis.

### Advantages
- Fast and reliable data storage and management.
- SQL is a declarative language, which optimizes your queries automatically in a way that imperative languages cannot. SQL will be almost certainly faster than Python scripts that parse data from disk!
- All data stored in a single binary file, keeping your data organized, tidy and much easier to share.
- Materialize intermediate results efficiently to speed up your data analysis.
- Speed up your code automatically using indices.

## Getting Started

### Installation

To start using PandasDB, simply install the library using pip:

```
pip install PandasDB
```

Once the library is installed, you can start using it in your Python projects or Jupyter notebooks.

### Basic usage
This script defines the most basic usage of the library. The raw data must be imported in the database only once.
```py
from pandasdb import PandasDB

# Create/open database
db = PandasDB("my_database.sql")

# Import raw data -- must only be done once!

# Import example CSV data
db.import_data("table_1", "my_csv.csv", format="csv")

# Import example excel table
db.import_data("table_2", "my_excel.xls", format="excel")

# Execute query with no return value
db.execute("INSERT INTO table_1 VALUES (...)")

# Query dataframe with return values
df = db.query("SELECT * FROM \"table_1\"")
```

For a more comprehensive showcase of features, check out the examples in the examples directory to get started.