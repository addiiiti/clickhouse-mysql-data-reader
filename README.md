# clickhouse-mysql-data-reader


## Overview

This project is a comprehensive tool for reading data from MySQL and writing it to ClickHouse, with various utilities for conversion, configuration, and data processing. It provides a seamless data migration pathway between these two database systems with support for various data formats and transformation options.

## Features

- Real-time data replication from MySQL to ClickHouse
- Support for CSV import/export
- Connection pooling for improved performance
- Configurable data transformations
- Daemon mode for continuous operation
- Command-line interface with extensive options

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/clickhouse-mysql-data-reader.git

# Navigate to the project directory
cd clickhouse-mysql-data-reader

# Install dependencies
pip install -r requirements.txt

# Install the package
python setup.py install
```

## Usage

Basic usage example:

```python
from clickhouse_mysql.reader import MySQLReader
from clickhouse_mysql.writer import CHWriter

# Configure the reader
reader = MySQLReader({
    'host': 'localhost',
    'port': 3306,
    'user': 'root',
    'password': 'password',
    'db': 'database'
})

# Configure the writer
writer = CHWriter({
    'host': 'localhost',
    'port': 9000,
    'user': 'default',
    'password': '',
    'db': 'database'
})

# Start data migration
reader.read()
writer.write(reader.data)
```

For more detailed examples, check the `clickhouse_mysql_examples` directory.

## Configuration

The application can be configured using either command-line options or a configuration file:

```bash
# Using command-line options
clickhouse-mysql --src-host=localhost --src-user=root --src-password=password --dst-host=localhost

# Using a configuration file
clickhouse-mysql --config=clickhouse-mysql.conf
```

## Documentation

For comprehensive documentation, please refer to the `docs` directory:
- [User Manual](docs/manual.md)
- [Usage References](docs/usage-references.md)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

