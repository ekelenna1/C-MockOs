# MockOS

MockOS is a C++ implementation of a mock operating system that simulates a file system and command shell. It allows users to create, manage, and interact with files using a modular command-line interface. This project demonstrates advanced object-oriented architecture by implementing multiple Design Patterns to decouple the file system logic from the user interface.

## Features

* **File System Management:** Create, delete, read, and write files within a virtual environment.
* **Support for Multiple File Types:** Handles both plain text and image files using specialized visitor algorithms.
* **Password Protection:** Secure file access implemented via the Proxy pattern.
* **Macro Commands:** Support for complex operations like "Rename" (Copy + Remove) and "Touch-Edit" (Create + Append).
* **Design Pattern Implementation:**
    * **Command Pattern** for extensible shell commands.
    * **Visitor Pattern** for file rendering and metadata retrieval.
    * **Composite Pattern** for chaining multiple commands.
    * **Strategy Pattern** for dynamic argument parsing.

## Getting Started

### Prerequisites

* CMake (version 3.20 or higher)
* C++14 compatible compiler (GCC, Clang, or MSVC)

### Building the Project

1.  Clone the repository:
    ```bash
    git clone [https://github.com/ekelenna1/C-MockOs.git](https://github.com/ekelenna1/C-MockOs.git)
    cd C-MockOs
    ```

2.  Create a build directory and navigate to it:
    ```bash
    mkdir build
    cd build
    ```

3.  Generate the build files with CMake:
    ```bash
    cmake ..
    ```

4.  Build the project:
    ```bash
    cmake --build .
    ```

### Running the Tests

To run the unit tests and verify system integrity, execute the following command from the `build` directory:

```bash
ctest
```

### Running the MockOS
After building the project, you can run the MockOS shell:
```bash
./src/Studio21
```

### Usage
MockOS provides a command-line interface with various commands for file and system management. Here are the available commands:

touch <filename> : Create a new file.

ls : List all files currently in the system.

ls -m : List files with detailed metadata.

cat <filename> [-a] : specific file contents. Use -a to append data.

ds <filename> [-d] : Display file contents (formatted). Use -d for raw data.

rm <filename> : Remove a file from the system.

cp <source> <destination> : Copy an existing file to a new name.

rn <oldname> <newname> : Rename a file (Macro command).

te <filename> : Touch and then immediately edit a file (Macro command).

### Project Structure
include/ : Header files defining the public API and interfaces.

lib/ : Source files for the MockOS static library implementation.

src/ : Main source files for the executable shell and lab runners.

tests/ : Unit tests using the GoogleTest framework.

docs/ : Documentation and studio answers.
