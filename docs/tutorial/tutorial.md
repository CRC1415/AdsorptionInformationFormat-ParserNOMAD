# Tutorial - Introduction

This tutorial will guide you through the process of using the AIF parser plugin with NOMAD.

## Getting Started

To get started with the AIF parser, you'll need to:

1. Install the plugin in your NOMAD environment
2. Parse AIF files using the NOMAD CLI or API
3. Access the structured data through NOMAD's GUI or API

## Installing the Plugin

First, you need to install the plugin in your NOMAD environment:

```bash
# Activate your virtual environment
source .pyenv/bin/activate

# Install the plugin in development mode
uv pip install -e '.[dev]'
```

## Parsing AIF Files

Once installed, you can parse AIF files using the NOMAD CLI:

```bash
# Parse a single AIF file
nomad parse tests/data/dut_134_scd_n2_77k.aif > parsed.json

# Run tests to validate the parser
python -m pytest -sv tests
```

## Using in NOMAD GUI

After installation, the plugin becomes available in your NOMAD instance. You can:

1. Upload AIF files directly to NOMAD
2. Query parsed data using NOMAD's search capabilities
3. Visualize adsorption data through NOMAD's built-in plotting tools

## Example Queries

Once data is parsed and uploaded to NOMAD, you can perform queries like:

```python
# Find all experiments with a specific operator
aifparser.schema_packages.aif_schema_package.AdsorptionInformationFile.aif_operator == "Volo"

# Search for experiments with specific adsorptive
aif_adsorptive == "N2"

# Find experiments with temperature data
data.aif_temperature = *
```

## Viewing Documentation

To view the documentation locally:

```bash
# Install documentation dependencies
uv pip install -r requirements_docs.txt

# Serve the documentation
mkdocs serve
```

## Next Steps

- Explore the reference documentation for detailed schema information
- Try parsing your own AIF files
- Learn about advanced querying capabilities in NOMAD
