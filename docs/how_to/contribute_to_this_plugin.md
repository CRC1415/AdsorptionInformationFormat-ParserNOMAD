# Contribute to This Plugin

We welcome contributions to improve the AIF parser plugin! This guide explains how to contribute to the project.

## How to Contribute

### Reporting Issues

If you find a bug or have a feature request:

1. Check if the issue already exists in our [GitHub issues tracker](https://github.com/CRC1415/AdsorptionInformationFormat-ParserNOMAD/issues)
2. Create a new issue with a clear description and reproduction steps
3. Include relevant information such as:
    
    - AIF file sample (if applicable)
    - Error messages
    - Python/NOMAD versions
    - Expected vs actual behavior

### Submitting Pull Requests

To submit code changes:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Run the test suite
6. Submit a pull request with a clear description

## Development Setup

To set up a development environment:

```bash
# Clone the repository
git clone https://github.com/Bondoki/aifparser.git
cd aifparser

# Create virtual environment
python3.12 -m venv .pyenv
source .pyenv/bin/activate

# Install development dependencies
uv pip install -e '.[dev]'

# Install pre-commit hooks
pip install pre-commit
pre-commit install
```

## Code Style and Standards

### Python Coding Standards

- Follow PEP 8 style guidelines
- Use docstrings for all public functions and classes
- Write type hints where appropriate
- Keep functions focused and well-tested

### Linting and Formatting

The project uses Ruff for linting and formatting:

```bash
# Check for linting issues
ruff check .

# Format code
ruff format .

# Both checks and format
ruff check . && ruff format .
```

### Testing

All contributions must include appropriate tests:

```bash
# Run all tests
python -m pytest -sv tests

# Run tests with coverage
uv pip install pytest-cov
python -m pytest --cov=src tests
```

## Documentation

Documentation improvements are always welcome:

1. Update the MkDocs documentation in the `docs/` directory
2. Ensure consistency with existing documentation style
3. Include examples where appropriate
4. Run `mkdocs serve` to preview documentation changes

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/).

## Release Process

Releases are managed through GitHub and PyPI:

1. Update version in `pyproject.toml`
2. Create a git tag
3. Push to GitHub
4. Build and publish to PyPI

## Contact

For questions about contributing, please contact:

- Ron Dockhorn <ron.dockhorn@tu-dresden.de>

## Resources

- [NOMAD Plugin Documentation](https://nomad-lab.eu/prod/v1/staging/docs/howto/plugins/plugins.html)
- [AIF Format Specification](https://github.com/AIF-development-team/adsorptioninformationformat)
- [NOMAD Support](https://nomad-lab.eu/nomad-lab/support.html)
