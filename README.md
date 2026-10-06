# Birmingham Healthy Life Expectancy

I am exploring differences in healthy life expectancy across Birmingham and its surrounding areas. HLE is my entry point: I map the variation, then investigate which social, economic, cultural and environmental characteristics might help me understand it.

## Exploration and data preparation

My [first notebook](notebooks/data-preparation/01_Data_Preparation.ipynb) explains the source data, geographical selection, field choices and checks. It includes saved outputs so I can read the preparation without running it first.

I have prepared HLE, household deprivation, overcrowding, fuel poverty, pollution, economic activity, qualifications, income, ethnicity and recorded crime. My [cleaned tables](data/cleaned/) use the same 660 MSOA codes and familiar local names. Supporting files retain counts, uncertainty and calculation evidence. This coverage is a starting envelope, not a settled final study boundary. I have not tested associations or fitted models yet.

Crime remains provisional: repeated identifiers need review, and the 2024 records use a Census 2021 population denominator. HLE covers 2019–2023; the notebook explains timing differences for supplementary sources.

## Run the notebook

I prepared and checked the notebook with Python 3.14.7. To reproduce it, install the packages in `requirements.txt` into a virtual environment and select that environment as the Jupyter kernel:

```bash
python -m pip install -r requirements.txt
```

Open `notebooks/data-preparation/01_Data_Preparation.ipynb` and run its cells in order. The notebook finds the repository’s data folder using relative paths. Reruns retain backups before replacing existing generated tables.

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
