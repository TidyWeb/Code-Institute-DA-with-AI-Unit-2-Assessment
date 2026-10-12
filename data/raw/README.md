# Raw source files

These are the source files read by the published notebooks. The source register records each file's source, period, geography, checksum, licence and notebook use.

- `2026-10-01/`: healthy life expectancy, Census TS007A, TS011, TS052, TS066 and TS067, fuel poverty, the two Defra pollution grids, MSOA boundaries, and the seven ONS query results used to build the geography lookup in `../prepared/Geography/`.
- `2026-10-06/`: Census TS021, household income and police recorded crime. The README in that folder gives the source details.
- `Nomis/`: 39 additional Census 2021 bulk archives used by Notebook 06, plus `census_screen_sources.csv`, which records the screen's retrieved tables. Five archives already used by earlier notebooks remain in the dated folders, so they are not duplicated here. TS008 was screened but had no usable total denominator.
- `FEAT/`: the June 2023 takeaway-count export used in Notebook 06. FEAT uses 2011 MSOA boundaries, so nine of the 660 study codes have no matching record and remain blank.

The other downloaded childhood and adult health, deprivation and railway datasets are not read by the published notebooks, so they are not included.
