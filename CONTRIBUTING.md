# Contributing to mise-valkey

Thank you for your interest in contributing to mise-valkey! This document provides guidelines and instructions to help you get started.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Environment](#development-environment)
- [Making Changes](#making-changes)
- [Testing Your Changes](#testing-your-changes)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Review Process](#review-process)
- [Style Guidelines](#style-guidelines)

## Code of Conduct

Please be respectful and considerate of others when contributing to this project. We aim to foster an inclusive and welcoming community.

## Getting Started

1. Fork the repository on GitHub
2. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/mise-valkey.git
   cd mise-valkey
   ```
3. Add the original repository as upstream:
   ```bash
   git remote add upstream https://github.com/roharon/mise-valkey.git
   ```

## Development Environment

### Requirements

- Bash 4.0 or higher
- [mise](https://github.com/jdx/mise) installed
- curl or wget for downloading files
- Basic knowledge of shell scripting

### Local Setup

1. Link your local copy of the plugin with mise:
   ```bash
   mise plugins link valkey .
   ```

2. Test the plugin by installing a version:
   ```bash
   mise install valkey@latest
   ```

## Making Changes

1. Create a new branch for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. Make your changes to the codebase.

3. Keep the following in mind:
   - The `bin/list-all` script should list all available versions of Valkey
   - The `bin/install` script handles downloading and installing a specific version
   - Avoid adding dependencies that are not commonly available in standard Linux/macOS distributions
   - Maintain backward compatibility with existing usage

4. Commit your changes with a descriptive message:
   ```bash
   git commit -m "Add feature: your feature description"
   ```

## Testing Your Changes

Test your changes thoroughly before submitting a pull request:

1. Test listing available versions:
   ```bash
   mise ls-remote valkey
   ```

2. Test installing a specific version:
   ```bash
   mise install valkey@7.2.9
   ```

3. Test using the installed version:
   ```bash
   mise exec valkey@7.2.9 -- valkey-server --version
   ```

4. Test on different platforms if possible (Linux, macOS, etc.)

## Submitting a Pull Request

1. Push your changes to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```

2. Open a pull request on GitHub.

3. In your pull request description:
   - Clearly describe what your changes do
   - Reference any related issues
   - Mention any breaking changes
   - Include screenshots or terminal output if relevant

## Review Process

1. Maintainers will review your pull request
2. Address any feedback or requested changes
3. Once approved, your changes will be merged into the main branch

## Style Guidelines

### Shell Script Style

- Use spaces, not tabs
- Use 2-space indentation
- Always use `set -euo pipefail` at the beginning of scripts
- Add comments for complex logic
- Use lowercase for variable names
- Use uppercase for constants
- Quote all variables to prevent word splitting

### Commit Messages

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less
- Reference issues and pull requests after the first line

## Thank You!

Your contributions help make mise-valkey better for everyone. We appreciate your time and effort!