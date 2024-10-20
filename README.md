# VSCODE Setup Environment for Competitive Programming

```markdown
# VSCode Tasks for C++ Compilation and Execution

This project uses a `tasks.json` file in Visual Studio Code to streamline the process of compiling and running C++ programs. Below is a breakdown of the tasks and how to use them.

## Prerequisites

- **g++**: Ensure that `g++` is installed on your system to compile C++ programs.
  You can install it using the following command:
  ```bash
  sudo apt install g++
  ```

- **Visual Studio Code**: You should have VSCode installed with the C++ extensions for syntax highlighting and better development experience.

- **input.txt**: This file should exist in the same directory as your C++ file if you want to redirect input during execution.

## Tasks Overview

The `tasks.json` provides two tasks: one for compiling the C++ code, and another for compiling and running it in one step.

### 1. Compile Task

- **Label**: `compile`
- **Command**: This task compiles the currently open C++ file using the following command:
  ```bash
  g++ -std=c++17 -o <filename without extension> <file path>
  ```
  - **Input**: The open C++ file in the editor.
  - **Output**: An executable file with the same name as the C++ source file (but without the `.cpp` extension).

#### How to Use:
1. Open your `.cpp` file in VSCode.
2. Press `Ctrl+Shift+B` and select the `compile` task.
3. The compiled executable will be created in the same directory as your source file.

### 2. Compile and Run Task

- **Label**: `compile and run`
- **Command**: This task compiles and then runs the program, redirecting input from `input.txt` and outputting to `output.txt`.
  ```bash
  g++ -std=c++17 -o <filename without extension> <file path> && ./<filename without extension> < input.txt > output.txt
  ```
  - **Input**: The currently open `.cpp` file in the editor, and `input.txt` if present.
  - **Output**: The output will be saved to `output.txt` in the same directory as the C++ file.

#### How to Use:
1. Open your `.cpp` file in VSCode.
2. Make sure you have an `input.txt` file in the same directory.
3. Press `Ctrl+Shift+B` and select the `compile and run` task.
4. The program will be compiled and executed, with input read from `input.txt` and output written to `output.txt`.

## Notes

- **File Paths**: This `tasks.json` file handles file paths with spaces (e.g., directories like `Programming for Career`), so ensure that your project files are structured correctly.
- **Input/Output Redirection**: The program expects `input.txt` to be present for input redirection. You can modify the task for different input/output needs.

## Troubleshooting

- **No such file or directory**: Ensure that the paths in the `input.txt` and `output.txt` files are correct.
- **Compile Errors**: Check that your C++ code does not contain syntax errors by looking at the terminal output when running the `compile` task.
