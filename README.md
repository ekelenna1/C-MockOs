# C++ Mock Operating System (OOP Showcase)

### Overview
This project is a modular, object-oriented simulation of a file system and command shell, built from scratch in **C++14**. It simulates core operating system functionalities—including file creation, editing, concatenation, and deletion—while enforcing strict architectural separation between interfaces and implementations.

The primary goal of this system was to implement robust **Design Patterns** to handle complex dependencies and extendability, rather than just writing a functional script.

### Key Design Patterns Implemented
This project heavily utilizes behavioral and creational design patterns to decouple components:

* **Command Pattern:** Encapsulates user requests (like `cat`, `ls`, `rm`) as objects (`AbstractCommand`), allowing for parameterization of the `CommandPrompt` invoker.
* **Visitor Pattern:** Separates algorithms from object structures. The `BasicDisplayVisitor` can traverse different file types (`TextFile`, `ImageFile`) to render them without modifying their class logic.
* **Strategy Pattern:** Enables interchangeable parsing algorithms. `TouchEditParsingStrategy` allows the system to dynamically switch how it interprets user input for complex macro-commands.
* **Abstract Factory Pattern:** Provides an interface `AbstractFileFactory` to create families of related file objects without specifying their concrete classes.
* **Prototype Pattern:** Implements a `clone()` method in `AbstractFile`, allowing efficient duplication of file objects at runtime.

### System Architecture
* **File System:** Manages the lifecycle of `AbstractFile` objects, supporting read/write streams (`vector<char>`) and password protection.
* **Command Shell:** A continuous loop that parses user input, maps strings to concrete `Command` objects, and executes them against the file system.
* **Error Handling:** A robust custom error enumeration (`ErrorTypes`) handles edge cases like allocation failures, circular dependencies, and permission denials.

### Technologies Used
* **Language:** C++14
* **Build System:** CMake
* **Testing:** GoogleTest (Unit Testing Framework)
* **Version Control:** Git
