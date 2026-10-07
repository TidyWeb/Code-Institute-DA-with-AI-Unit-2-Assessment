# Birmingham Healthy Life Expectancy

I am exploring differences in healthy life expectancy across Birmingham and its surrounding areas. HLE is my entry point: I map the variation, then investigate which social, economic, cultural and environmental characteristics might help me understand it.

## Source exploration and data preparation

1. [Notebook 01 — Source Exploration](notebooks/A%20%E2%80%94%20Source%20Exploration/01_Source_Exploration.ipynb) explores HLE first: the national profile, the 660-area coverage, male/female differences, confidence intervals, imputation and neighbouring-area contrasts. Saved outputs, profiling charts and the [interactive HLE profile](reports/ydata/hle---msoa-rows.html) accompany it. Download the HTML report and open it in a browser to use its interactive controls.
2. [Notebook 02 — Data Preparation](notebooks/B%20%E2%80%94%20Data%20Preparation/02_Data_Preparation.ipynb) prepares HLE, household deprivation, overcrowding, fuel poverty, pollution, economic activity, qualifications, income, ethnicity and recorded crime. It records source fields, calculations, checks and saved outputs.

My [cleaned tables](data/cleaned/) use the same 660 MSOA codes and familiar local names. Supporting files retain counts and calculation evidence. This coverage is a starting envelope, not a settled final study boundary.

The [saved modelling flags](data/cleaned/Modelling%20Flags/modelling_flags_msoa.csv) identify six visitor hubs for exclusion from crime analysis only. Student areas remain in every dataset with a caveat; no area is removed from the source tables. Crime remains provisional: repeated identifiers and the Census 2021 population denominator need care. HLE covers 2019–2023; supplementary measures use different periods.

Notebook 03 has been run locally and awaits review before publication. These two published notebooks cover source exploration and preparation; they do not fit a model or establish causal relationships.

## Run the notebooks

I prepared and checked these notebooks with Python 3.14.7. To reproduce them, install the packages in `requirements.txt` into a virtual environment and select that environment as the Jupyter kernel:

```bash
python -m pip install -r requirements.txt
```

Open either notebook from its own A or B folder and run its cells in order. Both locate the repository's data folder using relative paths. Notebook 01 reads the supplied profiling report and charts; generating that report again is not required. Notebook 02 retains backups before replacing existing generated tables.

## Data and sources

- [Raw sources](data/raw/) retain the publisher files in dated folders.
- [Cleaned tables and supporting evidence](data/cleaned/) hold my prepared outputs.
- [Reference names](data/reference/Area%20Names/) retain the locality lookup and its attribution.
- [Prepared geography](data/prepared/Geography/) supplies the LSOA-to-MSOA bridge.
- The [source register](data/source-register.csv) records the original collection’s links, dates, geography, checksums and licensing notes. The [additional-source note](data/raw/2026-10-06/README.md) and accompanying provenance files describe income, ethnicity and crime.

## Attribution

I credit ONS/Nomis for Census, HLE, income and geography data; DESNZ for fuel poverty; Defra for pollution; and Police.uk and the supplying forces for recorded crime and ASB. I retain the source files and source links. Public-sector datasets are supplied under their stated Open Government Licence terms; the ONS boundaries also require Ordnance Survey attribution.

My familiar MSOA labels adapt the House of Commons Library MSOA Names lookup under the [Open Parliament Licence](https://www.parliament.uk/site-information/copyright-parliament/open-parliament-licence/). Labels remain provisional and do not change statistical boundaries.

The earlier railway extract is © OpenStreetMap contributors under the [Open Database Licence](https://www.openstreetmap.org/copyright). It is not used by this preparation notebook.
