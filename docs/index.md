# Welcome to the `aifparser` documentation

Parser for the `.aif` file (Adsorption Information Format) for NOMAD generating an `.archive.json` entry based on [NOMAD Schema](https://nomad-lab.eu/prod/v1/docs/howto/plugins/types/schema_packages.html).

## Introduction

The Adsorption Information Format (AIF) is a standardized archive format for adsorption data, designed to ensure consistent reporting of porous materials adsorption experiments. It was developed to address the need for a universal standard for archiving adsorption data, as outlined in the referenced publications.

The AIF format enables researchers to store and share adsorption data in a structured, machine-readable format that supports both experimental measurements and computational simulations. This NOMAD plugin facilitates the parsing and integration of AIF files into the NOMAD ecosystem, allowing for seamless data management, visualization, and analysis.

## Key Features

- Parses AIF files and converts them to NOMAD-compatible schema
- Handles both adsorption and desorption data
- Supports unit conversion for pressure, temperature, mass, density, and time
- Generates visualizations of adsorption/desorption isotherms
- Integrates with NOMAD's data model and querying capabilities


<div markdown="block" class="home-grid">
<div markdown="block">

### Tutorial

To get started with the AIF parser, check out:

- [Introduction](tutorial/tutorial.md)
- [Using in NOMAD GUI](tutorial/using_in_nomad_gui.md)

</div>
<div markdown="block">

### How-to guides

How-to guides provide step-by-step instructions for a wide range of tasks, with the overarching topics:

- [Install this plugin](how_to/install_this_plugin.md)
- [Use this plugin](how_to/use_this_plugin.md)
- [Contribute to this plugin](how_to/contribute_to_this_plugin.md)
- [Contribute to the documentation](how_to/contribute_to_the_documentation.md)

</div>

<div markdown="block">

### Explanation

The explanation [section](explanation/explanation.md) provides background knowledge on this plugin.

</div>
<div markdown="block">

### Reference

The reference [section](reference/references.md) includes all CLI commands and arguments, all configuration options,
the possible schema annotations and their arguments, and a glossary of used terms.

</div>
</div>

## References

- [A Universal Standard Archive File for Adsorption Data](https://pubs.acs.org/doi/10.1021/acs.langmuir.1c00122)
- [Best-Practice Reporting for Porous Materials Adsorption Data](https://onlinelibrary.wiley.com/doi/10.1002/anie.202513606)
- [AIF Development Team Repository](https://github.com/AIF-development-team/adsorptioninformationformat)
- [AIF Official Website](https://adsorptioninformationformat.com/)
