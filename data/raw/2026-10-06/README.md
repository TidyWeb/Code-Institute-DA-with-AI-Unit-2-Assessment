# Additional supplementary datasets for deeper context

I am investigating cultural factors alongside socioeconomic factors as I explore differences in healthy life expectancy across Birmingham and the surrounding areas. These three open datasets give me more context to examine, rather than an explanation decided in advance.

## Ethnicity — Census 2021, TS021

I am adding ethnicity as one aspect of cultural context. The Census records residents’ self-reported ethnic groups; it does not directly measure beliefs, habits or cultural practices. I will examine area composition alongside the other features, without treating ethnicity as a cause of HLE differences or assuming that everyone in a group shares the same culture.

The raw Nomis ZIP includes MSOA counts and other published geographies. I will use the MSOA file, inspect its categories, and then decide which percentages are useful. Census Day was 21 March 2021, within the HLE period of 2019–2023. This open snapshot replaces the proposed safeguarded modelled ethnicity dataset.

Source: https://www.nomisweb.co.uk/output/census/2021/census2021-ts021.zip
Definitions: https://www.ons.gov.uk/datasets/TS021/editions/2021/versions/3

## Household income — financial year ending 2023

I am adding income to explore the financial resources available to households. The ONS workbook contains four modelled MSOA income measures, including income before and after housing costs, with confidence intervals. I will inspect these before choosing a compact set. Income is useful financial context, but it is not a direct measure of debt.

Source: https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/earningsandworkinghours/datasets/smallareaincomeestimatesformiddlelayersuperoutputareasenglandandwales

## Police recorded crime — January to December 2024

I am adding recorded crime as context about the local environment. I have requested the published crime CSVs for West Midlands, West Mercia, Staffordshire, Warwickshire, Derbyshire, Leicestershire and British Transport Police, retaining all source columns and locations at this stage. The regional forces cover the study envelope; transport police provide an additional source of incidents.

The download uses 2021 LSOA codes. I will check geographical coverage and reporting gaps before aggregating to MSOAs. Missing locations must not become zero crime, and recorded incidents are not a complete measure of all crime. Anti-social behaviour is included in the source and needs separate consideration.

2024 is a complete calendar year available from the current download service. It is later than the HLE period, so I will treat it as later contextual evidence rather than a contemporaneous explanation. The “2021” in LSOA geography describes the boundary vintage, not the crime year.

Source and licence: https://data.police.uk/about/
Download service: https://data.police.uk/data/

## Next step

I will apply the same preparation process to each dataset: inspect the source fields, keep the relevant geographical areas, select useful feature columns, and save a compact cleaned table. These raw downloads have not been cleaned or joined to HLE. All three sources are published under the Open Government Licence v3.0; provenance files retain download details and checksums.
