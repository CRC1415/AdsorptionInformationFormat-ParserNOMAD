# Install This Plugin

This guide explains how to install the AIF parser plugin in your NOMAD environment.

## Prerequisites

Before installing the plugin, ensure you have:

1. Python 3.10 or higher installed
2. A working NOMAD installation (version 1.4.2 or higher)
3. `uv` package manager installed (recommended for faster installations)

## Installation Methods

### Method 1: Development Installation (Recommended for Contributors)

To install the plugin in development mode with all dependencies:

```bash
# Clone the repository
git clone https://github.com/CRC1415/AdsorptionInformationFormat-ParserNOMAD.git aifparser
cd aifparser

# Create and activate virtual environment (optional but recommended)
python3.12 -m venv .pyenv
source .pyenv/bin/activate

# Upgrade pip
pip install --upgrade pip

# Install uv package manager
pip install uv

# Install the plugin in development mode with dev dependencies
uv pip install -e '.[dev]'
```

### Method 2: Direct Installation from GitHub

To install directly from the GitHub repository:

```bash
# Install directly from GitHub
uv pip install git+https://github.com/CRC1415/AdsorptionInformationFormat-ParserNOMAD.git
```

### Method 3: Using pip

If you prefer using pip directly:

```bash
# Install using pip
pip install git+https://github.com/CRC1415/AdsorptionInformationFormat-ParserNOMAD.git
```

## Verify Installation

After installation, verify that the plugin is correctly installed:

```bash
# Check that the plugin is recognized by NOMAD
nomad --help

# Run tests to ensure everything works
python -m pytest -sv tests
```

## Development Setup

For developers who want to contribute to the plugin:

1. Install the development dependencies:
```bash
uv pip install -e '.[dev]'
```

2. Run linters and formatters:
```bash
ruff check .
ruff format . --check
```

3. Run tests with coverage:
```bash
uv pip install pytest-cov
python -m pytest --cov=src tests
```

## Troubleshooting

### Common Issues

1. **Permission errors**: Make sure you're using the correct Python environment
2. **Missing dependencies**: Ensure all dependencies are installed using `uv pip install -e '.[dev]'`
3. **Version conflicts**: Make sure you're using compatible versions of NOMAD and Python

### Contact Information

If you encounter issues during installation, please contact:

- Ron Dockhorn <ron.dockhorn@tu-dresden.de>
