# C++ Unit Test Generator using LLM

This project is an AI-powered **Unit Test Generator Tool for C++ Applications**, designed to automate the creation and refinement of unit tests using a Large Language Model (LLM). The tool takes C++ source code as input and outputs optimized and high-coverage unit tests iteratively, incorporating build feedback and coverage data.

---

## 🚀 Features

- 🔍 Parses C++ code and extracts functions for testing
- 🤖 Generates unit tests using a Large Language Model
- 🔁 Refines test cases based on compiler errors and warnings
- 📈 Improves test coverage through feedback loops
- 🧪 Supports Google Test framework
- 🧠 Modular and extensible architecture for further improvements

---

## 🧱 Architecture

C++ Code Input
↓
Function Extractor ──▶ Prompt Generator
↓ ↓
LLM API ◀───────────────🧠
↓
Generated Unit Tests
↓
Build & Run with GTest
↓
Error/Coverage Analyzer
↓
Feedback Loop (Refine Tests)

yaml
Copy
Edit

---

## 📁 Project Structure

test-generator-cpp/
├── extractor/ # Extracts functions from C++ files
├── generator/ # Handles LLM interaction and prompt creation
├── compiler/ # Compiles and runs generated tests
├── analyzer/ # Parses errors and feedback
├── tests/ # Generated test files
├── main.py # Main controller script
├── config.yaml # Configuration settings
└── README.md # Project documentation

yaml
Copy
Edit

---

## ⚙️ Prerequisites

- Python 3.8+
- OpenAI Python SDK (or similar for LLM access)
- GoogleTest installed (for running tests)
- A C++ compiler (e.g., `g++`)

Install required Python dependencies:

```bash
pip install -r requirements.txt
```

## 🧪 How to Use
Place your C++ source file in the root directory or provide a path.

Configure the settings in config.yaml:

LLM model

Max tokens

Test template style (e.g., GoogleTest)

Run the generator:
``` bash 
python main.py --file path/to/your/code.cpp
```
Tests are generated inside the tests/ folder and compiled/executed automatically.

Review logs for any build errors or coverage metrics.

🔄 Feedback Loop
If the tests fail or don't cover enough edge cases:

The system collects error messages from the compiler

Analyzes the issues

Sends refined prompts to the LLM to generate improved test cases

## 📦 Example Output
Given a C++ file:

``` bash

int add(int a, int b) {
    return a + b;
}
```
Generated test:

```bash
TEST(AdditionTest, HandlesPositiveNumbers) {
    EXPECT_EQ(add(2, 3), 5);
}
```
