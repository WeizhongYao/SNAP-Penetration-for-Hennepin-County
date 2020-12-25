# SNAP-Penetration-for-Hennepin-County
>[Xinbo Wang](https://github.com/xinbo-hubert-wang), Farhad Mughal, Mark Chen, Weizhong Yao

Work in progress. Plan to complete before 2020.12.27

Please See the [Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiYzRmNTdjYWQtMDE4ZS00ZDYxLWFmYmMtNDZiYzZlMmNjMDdjIiwidCI6Ijc3YjRmOGFkLWY2MmEtNGUzYS05OWFmLTAwM2RhNzYwMDQ3YyIsImMiOjF9&pageName=ReportSection) for final results.

![png](dashboard_snapshot.png)

## Background

[SNAP](https://www.fns.usda.gov/snap/supplemental-nutrition-assistance-program) (Supplemental Nutrition Assistance Program), formerly yet still commonly known as the Food Stamp Program, is a federal program that provides food-purchasing assistance for low- and no-income people. (see [Wiki](https://en.wikipedia.org/wiki/Supplemental_Nutrition_Assistance_Program)).

As the most populous county in Minnesota (and where UoM is located), Hennepin County is interested in improving the SNAP program's coverage among eligible people within the county. However, without a clear definition of success, the county is struggling in their performance measurement and identifying where to start for improvement. 

Therefore, the county reached out to the university's Carlson Analytics Lab and made the problem a final live case for our first semester in the MSBA program. After several weeks' problem defining and solution developing, we delivered our presentation to the county on Dec 14. After the delivery, the county generously approved sharing the data and results online, which made it possible for publishing this repository. 

We recognize that the task of estimating eligibility itself is not easy and could use much more refinements, but the idea is to do it as accurately as possible so that further analysis and insights can have a sounder ground. This repository will serve as a means of sharing the technical details of our solution including the data pipeline, dashboard, and documentation. More importantly, we hope this could be a way for more people to know and become interested in the SNAP program, and potentially help improving the eligibility estimations. Other counties that are interested in their SNAP penetration rate might also find this repository helpful for inspiration.

## Data Sources

The repository mainly use three groups of data sources grouped by purposes:
1. Geographical data: including the geometries and land area data for the cities and tracts within the county.
2. SNAP registration data: generously provided by Hennepin County, down to the level for each month, tract, and race.
3. Census survey data: used for estimating eligibility by household income and adjustments.

## The Solution

Our solution is mainly divided into three parts in two notebooks and one Power BI dashboard.

1. Calculating the penetration rate, which is the core of this repository. The notebook [calculate_penetration_rate.ipynb](calculate_penetration_rate.ipynb) contains the full detail of our methodology as well as the data pipeline that guides you from data acquisition (mainly from the census API) to outputing the results.
2. Preparing the geo mapping and outputing the geojson files for visualization. This part is discussed in detail in the notebook [hennepin_tracts_geo_info.ipynb](hennepin_tracts_geo_info.ipynb).
3. The Power BI dashboard [pbix file](https://github.com/xinbo-hubert-wang/SNAP-Penetration-for-Hennepin-County/blob/main/SNAP%20Penetration%20Rate%20Dashboard.pbix), which is the development file of the [dashboard](https://app.powerbi.com/view?r=eyJrIjoiYzRmNTdjYWQtMDE4ZS00ZDYxLWFmYmMtNDZiYzZlMmNjMDdjIiwidCI6Ijc3YjRmOGFkLWY2MmEtNGUzYS05OWFmLTAwM2RhNzYwMDQ3YyIsImMiOjF9&pageName=ReportSection). To open the file in your computer, you need to first install [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) which is free for development purposes.
