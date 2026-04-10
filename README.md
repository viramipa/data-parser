# data-parser

## Description

`data-parser` is a versatile command-line tool and Python library designed to efficiently parse and transform data from various formats into a standardized structure. It offers flexible configuration options and supports multiple input and output types. Its primary goal is to simplify data processing pipelines by providing a reliable and easily integrable solution for data extraction, cleaning, and transformation.

## Features

*   **Multi-Format Support:** Parses data from CSV, JSON, XML, and plain text files.
*   **Customizable Parsing Rules:** Define custom parsing rules using regular expressions, delimiters, and XPath/JSONPath expressions.
*   **Data Transformation:** Applies transformations such as type conversion, data cleaning, and aggregation.
*   **Output Formatting:**  Supports outputting parsed data in JSON, CSV, or custom formats via templates.
*   **Command-Line Interface (CLI):**  Provides a user-friendly CLI for quick data parsing and transformation.
*   **Python Library:** Offers a Python API for integrating `data-parser` into existing Python applications.
*   **Error Handling:** Robust error handling and logging for identifying and resolving parsing issues.
*   **Schema Validation:** Optional schema validation against JSON Schema for data integrity.
*   **Extensible Architecture:** Supports custom input and output formats through plugin mechanisms.
*   **Configuration Management:** Load parsing configurations from YAML or JSON files.

## Technologies Used

*   **Python:** The core programming language used for development.
*   **`argparse`:** For command-line argument parsing.
*   **`json`:**  For handling JSON data.
*   **`csv`:** For handling CSV data.
*   **`xml.etree.ElementTree` (or `lxml` - optional):** For parsing XML data.  `lxml` is recommended for improved performance and security.
*   **`re`:** For regular expression-based parsing.
*   **`PyYAML`:** For reading configuration from YAML files.
*   **`jsonschema`:** For schema validation.
*   **`logging`:** For logging errors and informational messages.

## Installation

### Prerequisites

*   Python 3.7 or higher

### Using pip (Recommended)

```bash
pip install data-parser
```

To install with optional dependencies for XML parsing with `lxml` and YAML support with `PyYAML`:

```bash
pip install data-parser[xml,yaml]
```

To install with optional dependencies for schema validation with `jsonschema`:

```bash
pip install data-parser[schema]
```

To install all optional dependencies:

```bash
pip install data-parser[xml,yaml,schema]
```

### From Source

1.  Clone the repository:

    ```bash
    git clone https://github.com/your-username/data-parser.git
    ```

2.  Navigate to the project directory:

    ```bash
    cd data-parser
    ```

3.  Install using pip:

    ```bash
    pip install .
    ```

    To install with optional dependencies (e.g. `lxml` for faster XML parsing, `PyYAML` for YAML configuration, and `jsonschema` for schema validation):

    ```bash
    pip install .[xml,yaml,schema]
    ```

## Usage

### Command-Line Interface (CLI)

```bash
data-parser --input <input_file> --config <config_file> --output <output_file>
```

For detailed usage information:

```bash
data-parser --help
```

### Python Library

```python
from data_parser import DataParser

# Load configuration from file
parser = DataParser(config_file="config.yaml")

# Parse data from file
data = parser.parse_file("input.csv")

# Transform data
transformed_data = parser.transform_data(data)

# Output data to file
parser.output_data(transformed_data, "output.json")
```

## Configuration

Configuration files can be in YAML or JSON format.  A basic YAML configuration example:

```yaml
input_format: csv
output_format: json
delimiter: ','
fields:
  - name: id
    type: integer
  - name: name
    type: string
  - name: value
    type: float
```

Refer to the `docs/configuration.md` file (not included here) for detailed configuration options and examples.

## Contributing

Contributions are welcome! Please see the `CONTRIBUTING.md` file for guidelines.

## License

[MIT License](LICENSE)