# Raw source files

These are the untouched source files the notebooks read, kept in the dated folders they were downloaded into. Nothing here has been changed.

- `2026-10-01/`: healthy life expectancy, the Census tables (TS007A, TS011, TS052, TS066, TS067), fuel poverty, the two Defra pollution grids, the MSOA boundaries, and the seven ONS query results that built the geography lookup in `../prepared/Geography/`.
- `2026-10-06/`: ethnic group (Census TS021), household income and police recorded crime, each with a `.source.json` file recording where and when it was downloaded. Their [README](2026-10-06/README.md) explains why I added them.

`../source-register.csv` gives the source link, period, geography, checksum and licence for every file, and says which notebook uses it.

I downloaded several other datasets while I was exploring ideas: childhood and adult obesity, adult smoking, the 2025 Index of Multiple Deprivation, more Census tables, and railway lines and stations from the original rail-corridor idea. None of them made it into the analysis, so I've taken them out to keep the repository to what the notebooks actually use.
