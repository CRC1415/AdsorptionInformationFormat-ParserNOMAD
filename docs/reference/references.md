# References

This section includes all CLI commands, arguments, schema annotations, and a glossary of terms for the AIF parser plugin.

## CLI Commands

### Parsing AIF Files

```bash
# Parse a single AIF file
nomad parse <path-to-aif-file> [options]

# Parse and output to file
nomad parse tests/data/dut_134_scd_n2_77k.aif > parsed.json

# Run tests
python -m pytest -sv tests

# Run tests with coverage
python -m pytest --cov=src tests
```

## Schema Annotations

The AIF parser defines the following NOMAD schema annotations:

### AdsorptionInformationFile

The main schema section for AIF data:

- **aif_operator**: Name of the person who ran the experiment
- **aif_date**: Date of the experiment (ISO 8601 format)
- **aif_instrument**: Instrument used for the experiment
- **aif_adsorptive**: Name of the adsorptive substance
- **aif_adsorptive_name**: Secondary identifier for adsorptive
- **aif_temperature**: Experiment temperature
- **aif_method**: Method used to determine amount adsorbed
- **aif_isotherm_type**: Isotherm type (absolute, excess, net)
- **aif_saturation_pressure**: Saturation pressure at experiment temperature
- **aif_digitizer**: Person who digitized the experiment
- **aif_sample_mass**: Mass of the sample
- **aif_sample_density**: Density of the sample
- **aif_sample_id**: Unique identifying code for sample
- **aif_sample_material_id**: Designated name for the material
- **aif_info**: Secondary identifier
- **aif_hashkey**: Secondary identifier
- **aif_degas_summary**: Summary of degas conditions
- **aif_degas_temperature**: Degas temperature
- **aif_degas_time**: Degas time
- **aif_version**: Version of AIF data names
- **aif_citation_doi**: DOI of cited work
- **aif_citation_source**: Source of cited work
- **aif_simltn_code**: Simulation code identifier
- **aif_simltn_date**: Date of simulation
- **aif_simltn_size**: Simulation size parameters
- **aif_simltn_forcefield_adsorptive**: Adsorptive force field details
- **aif_simltn_forcefield_adsorbent**: Adsorbent force field details
- **aif_simltn_input_files**: Links to input files
- **aif_simltn_sampling**: Sampling algorithm used
- **aif_simltn_lot**: Level of theory used

### AdsorptionInformationFileData

Subsection for adsorption/desorption data:

- **aif_data_pressure**: Equilibrium pressure values
- **aif_data_fugacity**: Fugacity values
- **aif_data_saturation_pressure**: Saturation pressure values
- **aif_data_amount**: Amount adsorbed (loading)
- **aif_data_amount_excess**: Excess amount adsorbed
- **aif_data_amount_absolute**: Absolute amount adsorbed
- **aif_data_amount_net**: Net amount adsorbed
- **aif_data_enthalpy**: Enthalpy of adsorption/desorption

## Configuration Options

### Unit Handling

The parser supports automatic conversion of common unit abbreviations:

- **Pressure**: Torr, Pascal, Pa, kPa
- **Temperature**: K, k
- **Mass**: g, kg
- **Density**: g/cc, kg/cc
- **Time**: s, min, h
- **Loading**: MOL-PER-KiloGM, mmolg-1

## Glossary

### AIF (Adsorption Information File)
A standardized format for archiving adsorption data with consistent metadata and data structures.

### NOMAD
The National Open Science Data Infrastructure platform for materials science data management and analysis.

### Isotherm
A curve showing the relationship between pressure and amount adsorbed at constant temperature.

### Adsorption
The process by which molecules accumulate on the surface of a solid or liquid.

### Desorption
The process by which molecules are released from the surface of a solid or liquid.

### Loading
The amount of adsorbate per unit mass of adsorbent, typically expressed in mmol/g or mol/kg.

### Saturation Pressure
The pressure at which a gas is in equilibrium with its liquid phase at a given temperature.

### Force Field
A set of mathematical functions and parameters used to describe intermolecular interactions in molecular simulations.

### Unit Conversion
The process of converting physical quantities from one unit system to another (e.g., from Torr to kPa).

### Schema
A formal description of the structure and types of data that can be stored in a database or system.