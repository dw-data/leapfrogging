# Introduction

Today, the cheapest way to power a society, is green, clean, renewable
electricity. We’ll show the “fossil fuel detour” taken by the West, and
how some of the poorest countries in the world are building better from
the start.

*In this repository, you will find the methodology, data and code behind
the stories that came out of this analysis.*

**Explainer video:** [Youtube, DW Planet A: The unexpected way India is
beating the U.S.](https://www.youtube.com/watch?v=qoNr6hjy7aE) \|
[Instagram,
dw_environment](https://www.instagram.com/reels/DdWWH3hjF6j/)

**Online article:** [English](https://www.dw.com/a-79474847)

**Story by:** [Kira
Schacht](https://www.dw.com/en/kira-schacht/person-46893544)

- `analysis.Rmd` is the main file that contains the R code for the
  analysis
- `data/...` contains the raw data files used in the analysis

# Read data

## UN Country metadata

- [UN Country isocodes and continent/regional
  affiliations](https://unstats.un.org/unsd/methodology/m49/overview/)
- [World Bank income
  groups](https://datahelpdesk.worldbank.org/knowledgebase/articles/906519-world-bank-country-and-lending-groups)

## GDP data

[Penn World Table version
11.0](https://www.rug.nl/ggdc/productivity/pwt/?lang=en): Output-side
real GDP at chained PPPs (in mil. 2021US\$) per capita

## Historical energy data

[Primary, Final and Useful Energy Database
(PFUDB)](https://iiasa.ac.at/models-tools-data/pfudb): Final energy
consumption by source (TJ/y) and population (1000 persons), for select
regions & countries.

## IEA Energy Data

- Energy consumption by fuel
- Electricity generation by fuel

## Merge PFU data with IEA data

Check how similar the two datasets are:

![](analysis_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

## Merge energy data with GDP data, add country metadata

## Assign electricity and energy types to classes

| type | productLabel |
|:---|:---|
| fossil | Coal, Natural gas, Oil, Coal and coal products, Primary oil, Oil and oil products, Natural gas, Oil products |
| other | Biofuels, Nuclear, Other sources, Waste, Biofuels and waste, Heat, Nuclear |
| renewable | Geothermal, Solar thermal, Hydropower, Solar PV, Tide, Wind, Electricity, Solar, wind and other renewables, Hydropower |
| NA | Total |

# Energy consumption

## How did countries’ energy mixes change over time?

Total final consumption (TFC) by source over time

Energy consumption shares by source type: Fossil vs biomass vs
electricity&renewable

### US energy consumption by individual source

    ## # A tibble: 6 × 7
    ##    year   COAL   NATGAS  MTOTOIL  OTHER COMRENEW   ELECTR
    ##   <dbl>  <dbl>    <dbl>    <dbl>  <dbl>    <dbl>    <dbl>
    ## 1  2019 644740 16025952 31622507 379637  3590849 13787827
    ## 2  2020 540438 14932423 27963136 378756  3294752 13600044
    ## 3  2021 567856 15486875 30340529 371993  3484833 13817551
    ## 4  2022 553349 16148771 31085058 375062  3576353 14422350
    ## 5  2023 514065 16087157 30851540 382720  4011411 14019321
    ## 6  2024 474662 16149605 30642358 380813  3769590 14523510

### Baseline countries: USA, India, China, Vietnam, OECD

![](analysis_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

### By income groups

![](analysis_files/figure-gfm/unnamed-chunk-13-1.png)<!-- -->

### For online chart: Baseline countries and combined income groups

# Electricity mix over time

## Current electricity mix by country

    ## # A tibble: 5 × 2
    ##   income              renewable
    ##   <chr>                   <dbl>
    ## 1 High income             0.298
    ## 2 Low income              0.468
    ## 3 Lower middle income     0.372
    ## 4 Upper middle income     0.220
    ## 5 <NA>                    8.36

## Column chart of current electricity sources:

Income group averages, China, India, Vietnam, US, Global average

![](analysis_files/figure-gfm/unnamed-chunk-18-1.png)<!-- -->

## Solar power development in Africa

Source: [Ember yearly electricity
data](https://ember-energy.org/data/yearly-electricity-data/)

Ember includes more complete electricity data for African countries, and
includes figures for 2024.

![](analysis_files/figure-gfm/unnamed-chunk-19-1.png)<!-- -->

# Quality control disclaimer

The code used in this analysis was written by the author. For all of our
analyses, if any portion of the code is LLM-generated, this is flagged
in the script.

All code in this project has been reviewed pre-publication by both the
author as well as a second person to ensure quality.

Should you have any questions or notice errors or inconsistencies,
please reach out to <data-team@dw.com>.
