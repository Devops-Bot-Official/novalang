NovaLang is a lightweight, developer-friendly programming language designed for configuration and scripting purposes, tailored specifically for DevOps workflows and infrastructure as a service (IaaS) tools. NovaLang combines simplicity, readability, and flexibility, making it easier to manage and automate DevOps tasks.

---

## Features

1. **Simple Syntax**:
   - Use `=` for assignments, curly braces `{}` for blocks, and brackets `[]` for lists.
   
2. **Readable Configuration**:
   - Define structured data in an intuitive and concise way.

3. **Support for Common Data Types**:
   - Strings, numbers, booleans (`true`, `false`), null values, lists, and nested blocks.

4. **Custom Functions**:
   - Define reusable functions with named arguments.

5. **Includes**:
   - Modularize configurations by including external files.

6. **Comments**:
   - Use `#`, `//`, or multi-line comments `/* ... */`.

---

## Example NovaLang Code

```nova
# Single-line comment

/* Multi-line
   Comment */

include "common.nova"

var name = "John"
var age = 30
var hobbies = ["reading", "coding"]

user {
    name = name
    age = age
    hobbies = hobbies
}

fn greet(user) {
    print("Hello, " + user.name)
}
```

---

## Project Structure

```
novalang/
│
├── src/                # Source code for NovaLang
│   ├── lexer.py        # Lexer (tokenizer) for NovaLang
│   ├── parser.py       # Parser and AST generation
│   ├── transformer.py  # Handles transformations of parsed data
│   ├── interpreter.py  # Interpreter for executing NovaLang code
│   └── utils.py        # Utility functions (e.g., file handling, error logging)
│
├── grammars/           # Grammar definitions
│   └── novalang.lark   # NovaLang grammar (EBNF format)
│
├── examples/           # Example NovaLang scripts
│   ├── example1.nova   # Example script for testing
│   ├── example2.nova   # Another example script
│   └── complex.nova    # More complex example
│
├── tests/              # Unit and integration tests
│   ├── test_lexer.py   # Tests for the lexer
│   ├── test_parser.py  # Tests for the parser
│   ├── test_transformer.py  # Tests for transformations
│   ├── test_interpreter.py  # Tests for the interpreter
│   └── test_examples.py     # Tests using example scripts
│
├── main.py             # Entry point for running NovaLang scripts
│
├── requirements.txt    # Dependencies for the project
│
└── README.md           # Project description and usage instructions
```

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/novalang.git
   cd novalang
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

### Running a NovaLang Script

To execute a NovaLang script, use the following command:
```bash
python main.py <path-to-script>
```

For example:
```bash
python main.py examples/example1.nova
```

### Example Output
Given the `examples/example1.nova` script:
```nova
var name = "John"
var age = 30

user {
    name = name
    age = age
    hobbies = ["reading", "coding"]
}
```
The program will produce the output:
```
Setting name to John
Setting age to 30
Entering block user
```

---

## Language Syntax

### 1. Variables
Define variables using `var`:
```nova
var name = "NovaLang"
var count = 10
var active = true
```

### 2. Blocks
Group related statements using curly braces:
```nova
config {
    key = "value"
    nested {
        param = 42
    }
}
```

### 3. Lists
Define lists with brackets `[]`:
```nova
var items = ["item1", "item2", "item3"]
```

### 4. Functions
Define reusable functions:
```nova
fn greet(user) {
    print("Hello, " + user.name)
}
```

### 5. Includes
Modularize configurations with `include`:
```nova
include "common.nova"
```

### 6. Comments
- Single-line: `#` or `//`
- Multi-line: `/* ... */`

---

## Testing

Run the test suite to ensure everything works as expected:
```bash
pytest tests/
```

---

## Contributing

We welcome contributions! To contribute:
1. Fork the repository.
2. Create a feature branch.
3. Submit a pull request.

---

## License

This project is licensed under the MIT License.

