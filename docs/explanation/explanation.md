# Explanation

This section provides background knowledge on the Adsorption Information Format (AIF) format and the NOMAD plugin that parses it.

## What is the AIF Format?

The Adsorption Information Format (AIF) is a standardized archive format for adsorption data, developed to ensure consistent reporting of porous materials adsorption experiments. It provides a universal standard for archiving adsorption data as described in the referenced publications.

The AIF format addresses the challenges of inconsistent data representation in adsorption studies by providing a structured, machine-readable format that includes:

- Experimental metadata
- Sample information
- Adsorption/desorption data points
- Simulation data (when applicable)
- Citation and versioning information

## AIF Structure

The AIF format is organized into several logical sections:

### 1. Experimental Metadata
Contains information about the experiment setup, including:

- Operator details
- Experiment date and instrument used
- Adsorptive substance information
- Experimental conditions (temperature, method, etc.)

### 2. Sample Information
Describes the sample characteristics:

- Sample mass and density
- Unique identifiers
- Degassing conditions and summary

### 3. Adsorption/Desorption Data
The core data points including:

- Equilibrium pressures
- Loadings (amount adsorbed)
- Thermodynamic properties (enthalpy)
- Saturation pressures

### 4. Simulation Data
Information about computational simulations when applicable:

- Simulation codes and dates
- Force field details
- Input files and sampling methods

### 5. Citation and Versioning
References and version control information:

- DOI references
- Version tracking of the AIF format

## AIF Metadata Fields

### Unit Fields
| Field | NOMAD Equivalent | Description | Data Type |
|-------|------------------|-------------|-----------|
| `_units_pressure` | `aif_data_pressure_units` | Units for pressure measurements | string |
| `_units_temperature` | `aif_data_temperature_units` | Units for temperature measurements | string |
| `_units_mass` | `aif_data_mass_units` | Units for mass measurements | string |
| `_units_density` | `aif_data_density_units` | Units for density measurements | string |
| `_units_time` | `aif_data_time_units` | Units for time measurements | string |
| `_units_loading` | `aif_data_loading_units` | Units for loading measurements | string |
| `_units_energy` | `aif_data_energy_units` | Units for energy measurements | string |

### Experimental Metadata Fields

| Field | NOMAD Equivalent | Description | Data Type |
|-------|------------------|-------------|-----------|
| `_exptl_operator` | `aif_operator` | Name of the person who ran the experiment | string |
| `_exptl_date` | `aif_date` | Date of the experiment (ISO 8601 format) | datetime |
| `_exptl_instrument` | `aif_instrument` | Instrument used for the experiment | string |
| `_exptl_adsorptive` | `aif_adsorptive` | Name of the adsorptive substance | string |
| `_exptl_adsorptive_name` | `aif_adsorptive_name` | Secondary identifier for adsorptive | string |
| `_exptl_temperature` | `aif_temperature` | Experiment temperature | float |
| `_exptl_method` | `aif_method` | Method used to determine amount adsorbed | string |
| `_exptl_isotherm_type` | `aif_isotherm_type` | Isotherm type (absolute, excess, net) | string |
| `_exptl_p0` | `aif_saturation_pressure` | Saturation pressure at experiment temperature | float |
| `_exptl_digitizer` | `aif_digitizer` | Person who digitized the experiment | string |

### Sample Information Fields

| Field | NOMAD Equivalent | Description | Data Type |
|-------|------------------|-------------|-----------|
| `_adsnt_sample_mass` | `aif_sample_mass` | Mass of the sample | float |
| `_adsnt_sample_density` | `aif_sample_density` | Density of the sample | float |
| `_adsnt_sample_id` | `aif_sample_id` | Unique identifying code for sample | string |
| `_adsnt_material_id` | `aif_sample_material_id` | Designated name for the material | string |
| `_adsnt_info` | `aif_info` | Secondary identifier | string |
| `_adsnt_hashkey` | `aif_hashkey` | Secondary identifier | string |
| `_adsnt_degas_summary` | `aif_degas_summary` | Summary of degas conditions | string |
| `_adsnt_degas_temperature` | `aif_degas_temperature` | Degas temperature | float |
| `_adsnt_degas_time` | `aif_degas_time` | Degas time | float with unit |

### Adsorption/Desorption Data Fields

#### Pressure and Saturation Data
| Field | NOMAD Equivalent | Description | Data Type |
|-------|------------------|-------------|-----------|
| `_adsorp_pressure` / `_desorp_pressure` | `aif_data_pressure` | Equilibrium pressure | array of floats |
| `_adsorp_p0` / `_desorp_p0` | `aif_data_saturation_pressure` | Saturation pressure at experiment temperature | array of floats |
| `_adsorp_fugacity` / `_desorp_fugacity` | `aif_data_fugacity` | Fugacity values | array of floats |

#### Loading Data
| Field | NOMAD Equivalent | Description | Data Type |
|-------|------------------|-------------|-----------|
| `_adsorp_amount` / `_desorp_amount` | `aif_data_amount` | Amount adsorbed (loading) | array of floats |
| `_adsorp_loading` / `_desorp_loading` | `aif_data_amount` | Deprecated field for loading | array of floats |
| `_adsorp_amount_excess` / `_desorp_amount_excess` | `aif_data_amount_excess` | Excess amount adsorbed | array of floats |
| `_adsorp_amount_absolute` / `_desorp_amount_absolute` | `aif_data_amount_absolute` | Absolute amount adsorbed | array of floats |
| `_adsorp_amount_net` / `_desorp_amount_net` | `aif_data_amount_net` | Net amount adsorbed | array of floats |
| `_adsorp_enthalpy` / `_desorp_enthalpy` | `aif_data_enthalpy` | Enthalpy of adsorption/desorption | array of floats |


### Simulation Data Fields

| Field | NOMAD Equivalent | Description | Data Type |
|-------|------------------|-------------|-----------|
| `_simltn_code` | `aif_simltn_code` | Simulation code identifier | string |
| `_simltn_date` | `aif_simltn_date` | Date of simulation | datetime |
| `_simltn_size` | `aif_simltn_size` | Simulation size parameters | string |
| `_simltn_forcefield_adsorptive` | `aif_simltn_forcefield_adsorptive` | Adsorptive force field details | string |
| `_simltn_forcefield_adsorbent` | `aif_simltn_forcefield_adsorbent` | Adsorbent force field details | string |
| `_simltn_input_files` | `aif_simltn_input_files` | Links to input files | string |
| `_simltn_sampling` | `aif_simltn_sampling` | Sampling algorithm used | string |
| `_simltn_lot` | `aif_simltn_lot` | Level of theory used | string |

### Citation and Versioning Fields

| Field | NOMAD Equivalent | Description | Data Type |
|-------|------------------|-------------|-----------|
| `_audit_aif_version` | `aif_version` | Version of AIF data names | string |
| `_citation_doi` | `aif_citation_doi` | DOI of cited work | string |
| `_citation_source` | `aif_citation_source` | Source of cited work | string |

## Unit Handling in AIF

The AIF format supports flexible unit specification through various `_units_*` fields. These fields are crucial for proper data interpretation and conversion:

- **Pressure units**: Commonly "kPa", "torr", "Pa", "Pascal"
- **Temperature units**: Typically "K", "k", "kelvin"
- **Mass units**: Usually "g", "kg", "gram", "kilogram"
- **Density units**: Often "g/cc", "kg/cc", "gram/centimeter**3"
- **Time units**: Standard "s", "min", "h", "second", "minute", "hour"
- **Loading units**: Frequently "MOL-PER-KiloGM", "mmolg-1", "mol/kg", "mmol/g"
- **Energy units**: Commonly "KiloJ-PER-MOL", "kJ/mole"

The parser includes robust unit conversion logic to standardize these variations into NOMAD's standard unit system, ensuring compatibility across different data sources.

## NOMAD Integration

The AIF parser plugin integrates with NOMAD by:

1. Creating structured data in NOMAD's schema system
2. Supporting unit conversion for various physical quantities
3. Generating visualizations of adsorption data
4. Making data searchable through NOMAD's query system
5. Providing consistent metadata handling

## Best Practices

When working with AIF files and the NOMAD plugin:

1. Ensure all required metadata fields are populated
2. Use consistent unit naming conventions
3. Validate data integrity before parsing
4. Leverage NOMAD's search capabilities for data discovery
5. Take advantage of the plugin's visualization features for data analysis

## References

- [AIF Official Dictionary ](https://raw.githubusercontent.com/AIF-development-team/adsorptioninformationformat/refs/heads/master/aifdictionary.json)
- [AIF Development Team Repository](https://github.com/AIF-development-team/adsorptioninformationformat)
- [AIF Official Website](https://adsorptioninformationformat.com/)
- [A Universal Standard Archive File for Adsorption Data](https://pubs.acs.org/doi/10.1021/acs.langmuir.1c00122)
- [Best-Practice Reporting for Porous Materials Adsorption Data](https://onlinelibrary.wiley.com/doi/10.1002/anie.202513606)

