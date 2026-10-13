# Birmingham Healthy Life Expectancy

<!-- Visual additions: package badges and project map -->
<p align="center">
  <a href="https://www.python.org/"><img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&amp;logo=python&amp;logoColor=white"></a>
  <a href="https://jupyter.org/"><img alt="Jupyter" src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&amp;logo=jupyter&amp;logoColor=white"></a>
  <a href="https://geopandas.org/"><img alt="GeoPandas" src="https://img.shields.io/badge/GeoPandas-139C5A?style=for-the-badge&amp;logo=geopandas&amp;logoColor=white"></a>
  <a href="https://pandas.pydata.org/"><img alt="pandas" src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&amp;logo=pandas&amp;logoColor=white"></a>
  <a href="https://numpy.org/"><img alt="NumPy" src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&amp;logo=numpy&amp;logoColor=white"></a>
  <a href="https://scipy.org/"><img alt="SciPy" src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&amp;logo=scipy&amp;logoColor=white"></a>
  <a href="https://shapely.readthedocs.io/"><img alt="Shapely" src="https://img.shields.io/badge/Shapely-3D7A57?style=for-the-badge&amp;logo=shapely&amp;logoColor=white"></a>
  <a href="https://scikit-learn.org/"><img alt="scikit-learn" src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&amp;logo=scikitlearn&amp;logoColor=white"></a>
  <a href="https://matplotlib.org/"><img alt="Matplotlib" src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&amp;logo=matplotlib&amp;logoColor=white"></a>
  <a href="https://ipython.org/"><img alt="IPython" src="https://img.shields.io/badge/IPython-515151?style=for-the-badge&amp;logo=ipython&amp;logoColor=white"></a>
</p>
<p align="center">
  <img src="data/cleaned/Neighbours/figures/04_big_gap_neighbours_map.png" alt="Map of derived average healthy life expectancy across the West Midlands study area, with selected large-gap neighbour pairs outlined in red and an enlarged Birmingham detail view." width="100%">
</p>
<!-- End visual additions -->

Many data analysis assessment projects use general datasets from Kaggle, on things like credit card churn, car prices or health insurance, and they're fine for us newbies to show off our new skills. I'd been there and done that. I wanted to find a problem that was closer to home, more relevant to me and to those I love, and something I could direct and shape to ask and answer real questions about my here and now.

How many years can you expect to live in good health? In Birmingham and the areas around it, the answer depends a lot on where you live. Across 660 neighbourhoods, healthy life expectancy (HLE) runs from about 54 years to nearly 76. Some places that share a boundary are 14 to 16 years apart. I find that remarkable.

The idea came from a map of the London Tube that showed life expectancy at each station ([*Lives on the Line*](https://jcheshire.com/featured-maps/lives-on-the-line/), by James Cheshire and Oliver O'Brien). Stops a few minutes apart had very different health outcomes. I wanted to see whether my own city did the same. The more I looked, the more I cared about neighbouring areas rather than railway lines. The rail corridor idea became window dressing, not a fundamental part of the investigation, so I dumped it. Instead, I mapped HLE for every small area, tested whether the gaps between neighbours are real or just estimate noise, and then asked what else about an area lines up with them: income, qualifications, work, housing, air quality and crime. Machine learning comes last, to see how much of the pattern those measures account for and where they fall short.

Everything here describes areas, not people. A link between HLE and income in an area doesn't tell you about anyone who lives there, and it doesn't prove a cause.

## Start here

### [tidyweb.github.io/Birmingham-Healthy-Life](https://tidyweb.github.io/Birmingham-Healthy-Life/)

The website above is the real README. It tells the whole story of the project in short illustrated chapters, from the idea to what the data does and doesn't say. It also holds my interactive dashboard of HLE across the 660 areas, which I built in my own code because Tableau couldn't show what I wanted, and you can read all six notebooks there without running anything. This page is the map of the repository.

## The notebooks

Run them in order. Each one reads the previous one's saved outputs.

1. [01 Source Exploration](notebooks/A%20%E2%80%94%20Source%20Exploration/01_Source_Exploration.ipynb). The HLE data itself: how my areas compare with the rest of the country, men against women, margins of error, and the first look at gaps between neighbours. The [interactive HLE profile](reports/ydata/hle---msoa-rows.html) goes with it; download it and open it in a browser.
2. [02 Data Preparation](notebooks/B%20%E2%80%94%20Data%20Preparation/02_Data_Preparation.ipynb). Ten datasets cut down to the measures I need, one row per area: HLE, household deprivation, overcrowding, fuel poverty, pollution, economic activity, qualifications, income, ethnicity and recorded crime. It also flags student areas and city-centre visitor hubs.
3. [03 Joined Table and Exploration](notebooks/C%20%E2%80%94%20Joined%20Table%20and%20Exploration/03_Joined_Table_and_Exploration.ipynb). Everything joined into one table, then explored: what moves with HLE, which measures overlap, and a shortlist of seven to take forward.
4. [04 Hypothesis and Neighbour Gaps](notebooks/D%20%E2%80%94%20Hypothesis%20and%20Neighbour%20Gaps/04_Hypothesis_and_Neighbour_Gaps.ipynb). Are the gaps between neighbours real? A test against estimate noise, a check on how much neighbouring areas resemble each other, and the 95 biggest-gap pairs picked by a fixed rule.
5. [05 Machine Learning](notebooks/E%20%E2%80%94%20Machine%20Learning/05_Machine_Learning.ipynb). K-means clustering with HLE held out, then one linear regression tested on local authorities it hasn't seen, and a map of where it gets HLE wrong.
6. [06 Hotspots](notebooks/F%20%E2%80%94%20Hotspots/06_Hotspots.ipynb). I group the 95 big-gap neighbour pairs into patches, compare how often they cross local-authority boundaries, estimate within-authority patterns, and screen Census 2021 characteristics alongside FEAT takeaway rates. These are area-level associations, not causes.

## Repository layout

```
data/
  raw/          untouched source files, in dated folders, with a README
  prepared/     the LSOA-to-MSOA geography lookup
  reference/    familiar local area names and their attribution
  cleaned/      everything the notebooks produce, including Hotspots outputs
  source-register.csv   links, dates, geography, checksums and licences for each source
notebooks/      the notebooks, one folder each (A to F)
reports/ydata/  the interactive HLE profile used in Notebook 01
requirements.txt
```

## Running them

I built and checked these with Python 3.14.7. Install the packages into a virtual environment and select it as the Jupyter kernel:

```bash
python -m pip install -r requirements.txt
```

The notebooks find the `data` folder from wherever they're opened, so nothing depends on my machine's paths. Every source they need is in `data/raw`. Each run overwrites its own outputs in `data/cleaned`.

## Data and sources

- [Raw sources](data/raw/), in dated folders, organised by date and topic, with a [README](data/raw/README.md) and source register.
- [Cleaned tables](data/cleaned/), all keyed on the same 660 MSOA codes.
- [Local area names](data/reference/Area%20Names/), with their attribution.
- [Geography lookup](data/prepared/Geography/), LSOA to MSOA.
- The [source register](data/source-register.csv) records where each source came from, when, and under what licence.

HLE covers 2019 to 2023. The other measures come from 2021 to 2024, so they're not one snapshot in time.

## Ethics

This project doesn't raise any privacy issues. Every dataset is open, public data, published by the government and public bodies under open licences, and I didn't collect any data myself. Everything is at MSOA level, where each area holds roughly 5,000 to 15,000 residents, and every figure is a total, rate or estimate for the whole area. There are no records about individuals, so no one can be identified. ONS also applies disclosure control to its Census tables, and the police data is anonymised to approximate locations before release.

The one thing I've been careful about is how I describe places, because calling a neighbourhood "unhealthy" could stigmatise the people who live there. So I describe areas and not people, I say links and not causes, and I treat ethnic composition only as a description of who lives in an area for the purpose of investigating culture as a factor in HLE.

## Attribution

ONS and Nomis for Census, HLE, income and geography data; the MRC Epidemiology Unit at the University of Cambridge for FEAT; DESNZ for fuel poverty; Defra for pollution; Police.uk and the supplying forces for recorded crime and anti-social behaviour. Public-sector data is used under the Open Government Licence. The ONS boundaries also carry Ordnance Survey attribution.

My local area names adapt the House of Commons Library MSOA Names lookup under the [Open Parliament Licence](https://www.parliament.uk/site-information/copyright-parliament/open-parliament-licence/). They're labels only and don't change any boundary.

The project idea credits [*Lives on the Line*](https://jcheshire.com/featured-maps/lives-on-the-line/) by James Cheshire and Oliver O'Brien.
