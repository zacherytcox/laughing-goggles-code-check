# Linter and Formatter Checker Script

This Bash script automates the process of checking Python, Bash, and Terraform files for linting issues and formatting inconsistencies. It ensures that your code adheres to certain standards and provides easy commands to fix any issues.

## Features

- **Python**: Uses the `black` linter to check Python code.
- **Bash**: Uses `shellcheck` to check shell script files for syntax and style issues.
- **Terraform**: Uses `terraform fmt` to check and enforce formatting for Terraform files.

## Requirements

This script assumes that you have the following tools installed:
- **Python** (with `pip3` installed)
- **Brew** (for installing missing dependencies like `shellcheck` and `terraform`)
- **Terraform** (for checking Terraform files)

If any required tools are missing, the script will attempt to install them for you.

## Installation

**Clone the repository or download the script**:
   ```bash
   git clone <repository_url>
   cd <project_directory>
   ```
## Usage

To run the script, simply execute it from the command line:

```bash
./<script_name>.sh
```

## The script will perform the following checks:

1. **Check Python files**: It will check all Python files in the current directory using the `black` linter. If issues are found, it suggests running `black .` to fix them.

2. **Check Bash files**: It will check all `.sh` files using `shellcheck`. If any issues are found, they will be displayed.

3. **Check Terraform files**: It will check all Terraform files using `terraform fmt -check`. If any formatting issues are found, it suggests running `terraform fmt -recursive` to fix them.

## Dependencies

The script checks for and installs the following tools if they're not already installed:

- **black**: Python linter for code formatting
- **shellcheck**: Linter for shell scripts
- **terraform**: Tool for managing Terraform configuration files

If you don't have `brew` (Homebrew) installed, please install it from [https://brew.sh/](https://brew.sh/).

## Example Output

When you run the script, you might see output similar to the following:

```text
Checking Python files...
black . --check --no-color
Please run 'black .' to fix found issues.

Checking Bash files...
shellcheck --color=never <file>.sh

Checking Terraform files...
terraform fmt -check -recursive
Please run 'terraform fmt -recursive' to fix found issues.
