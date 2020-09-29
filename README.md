# CodeTemplate

This Project aim at providing a orgnanize code Template for c++ based project using CMake.

## project organization
 * cmake: folder to centralize (1) CMake macros and function and (2) CMake related configuration files.
 * include: folder to centralize libraries header files.
 * src: folder to centralize binaries (bin) and libraries source files.
 * tests: folder to centralize test data and source files

## usefull tools settings
The project setup some usefull tools:
 * .clang-format: configuration file for clang format. Code formater that can be installed in you IDE (https://clang.llvm.org/docs/ClangFormat.html).
 * .releaserc: configuration file to use semantic release (https://github.com/semantic-release/semantic-release).
 * .github: folder to centralize github (CI/CD) workflows.