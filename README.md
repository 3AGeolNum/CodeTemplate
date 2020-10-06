# CodeTemplate
This Project aim at providing a orgnanize code Template for c++ based project using CMake.

# CI/CD
github CI/CD are implemented in .github/workflow folder
Status: ![CI](https://github.com/ring-teaching/CodeTemplate/workflows/CI/badge.svg?branch=master) ![CD](https://github.com/ring-teaching/CodeTemplate/workflows/CD/badge.svg)

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
