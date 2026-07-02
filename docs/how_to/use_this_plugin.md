# How to Use This Plugin

This guide explains how to use the AIF parser plugin within a NOMAD environment.

## Adding the Plugin to NOMAD

The AIF parser plugin can be integrated into NOMAD in two main ways depending on your setup:

### For NOMAD Oasis Users

1. Follow the [NOMAD plugin documentation](https://nomad-lab.eu/prod/v1/staging/docs/howto/oasis/configure.html#plugins) for detailed instructions
2. Add the plugin to your NOMAD Oasis instance
3. Restart your NOMAD service to load the new plugin

### For Local NOMAD Installations

1. Install the plugin in your local NOMAD environment:
```bash
# Navigate to your NOMAD installation directory
cd /path/to/nomad

# Install the AIF parser plugin
uv pip install -e 'path/to/aifparser/[dev]'
```

2. Configure NOMAD to recognize the plugin by ensuring the plugin entry points are registered

## Parsing AIF Files

Once the plugin is installed and configured, you can parse AIF files in several ways:

### Using the NOMAD GUI

Please see the [Tutorial](tutorial/tutorial.md).

### Using the NOMAD CLI

```bash
# Parse a single AIF file
nomad parse tests/data/dut_134_scd_n2_77k.aif > parsed.json

# Parse multiple files
nomad parse *.aif
```

### Using Python API

```python
import nomad

# Parse an AIF file programmatically
with open('path/to/file.aif', 'r') as f:
    content = f.read()
    
# Process using NOMAD's parsing infrastructure
```

## Data Access and Querying

After parsing, the AIF data becomes accessible through NOMAD's data model:

### Searching Data

You can search for specific AIF data using NOMAD's query language:

```bash
# Find all experiments with a specific operator
data.aif_operator#aifparser.schema_packages.aif_schema_package.AdsorptionInformationFile == "TU DD"

# Search for experiments with specific adsorptive
aif_adsorptive == N2

# Find experiments with temperature data
data.aif_temperature = *

# Find experiments with a range
60 mg <= data.aif_sample_mass <= 140 mg
```

### Data Structure

Parsed AIF data follows this structure in NOMAD:

- **Main Section**: `AdsorptionInformationFile` containing metadata
- **Data Subsections**: `AdsorptionInformationFileData` for adsorption/desorption data
- **Units**: All physical quantities are properly converted and annotated with units

## Visualization

The plugin generates visualizations of adsorption data:

1. **Semilog plots** of adsorption/desorption data
2. **Lin-lin plots** of adsorption/desorption data
3. **Support for relative pressure calculations** when saturation pressure data is available

## Example Workflow

Here's a typical workflow for using the AIF parser:

1. **Prepare AIF files** with proper metadata
2. **Parse files** using `nomad parse`
3. **Upload to NOMAD** for storage and sharing
4. **Query and analyze** data using NOMAD's search capabilities
5. **Visualize** adsorption isotherms through NOMAD's GUI

## Testing the Plugin

To verify that your installation works correctly:

```bash
# Run the test suite
python -m pytest -sv tests

# Run tests with coverage
uv pip install pytest-cov
python -m pytest --cov=src tests
```

## Troubleshooting

### Common Issues

1. **Plugin not recognized**: Ensure the plugin is properly installed and registered in NOMAD
2. **Parsing errors**: Verify that AIF files are properly formatted according to the AIF specification
3. **Missing data**: Check that required metadata fields are populated in AIF files

### Contact Information

If you encounter issues during usage, please contact:

- Ron Dockhorn <ron.dockhorn@tu-dresden.de>
