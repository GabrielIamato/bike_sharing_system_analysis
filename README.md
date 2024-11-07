# Analysis of Bike-Sharing System in São Paulo

## Objectives
Bike-sharing systems, known for their environmental sustainability, offer advantages over individual bicycles, such as reduced concerns regarding maintenance and theft, increased versatility, and high availability (KON et al., 2022). These systems have been gaining traction and require statistical analyses to support strategic expansion to new regions.

The primary research objectives are:
- Identify usage patterns of bike-sharing stations in São Paulo.
- Understand the structures related to cycling, transport, and popular interest.
- Produce analyses to aid in the expansion of the system.

## Materials and Methods
The data for bike stations were sourced from São Paulo's bike-sharing system, in partnership with the BikeScience project. Additional data on cycling infrastructure and public transport were obtained from Geosampa. Points of Interest (POIs) related to health, leisure, education, and food were collected using the Google Places API, resulting in a sample of 4,933 POIs intersecting the bike-sharing system’s coverage area.

Python was used for the analysis, leveraging libraries such as:
- `pandas`
- `matplotlib`
- `scikit-learn`
- `folium`
- `shapely`
- `ipywidgets` (for modifying trip parameters and generating interactive maps)

### Data Preprocessing
- Missing data for stations (38 total) was supplemented using the CityBikes API.
- Outliers for “trip duration” (over 12 hours) were marked as null (LIMA, KON, 2023).
- Out of 12,176,873 records (from 01/2018 to 07/2023), 10,601,762 records (87%) were used after preprocessing.

### Analysis Methods
- Indices were normalized for visualization.
- Pearson Correlation was used for comparisons.
- Outliers were identified using the Interquartile Range (IQR) method.
- The `geopy` library was employed to intersect stations with POIs, public transport, and bike lanes within a 500m radius, allowing for visual and statistical comparison of these intersections with the number of trips.

## Results

The trip index was designed considering the existence time and available slots at each station to analyze trip frequency. Notable high-index areas included Itaim Bibi, Vila Olímpia, Pinheiros, Av. Paulista, and Av. Indianópolis. Areas with a low index included the USP Campus in Butantã, Brooklin, Sumaré, and Santana. Regions with frequent zero-trip days matched those with a low index. Av. Paulista was particularly notable, as most stations experienced daily use. One type of map generated highlights the intersections of transport hubs, with significant findings near R. Vergueiro, Av. Rebouças, Av. das Nações Unidas, and downtown São Paulo. These regions contrasted with areas with few intersections due to infrastructure limitations, leading to a low correlation index.


Cycling infrastructure was concentrated near downtown, Pinheiros, R. Vergueiro, and Av. Indianópolis. A positive correlation with the trip index was visible in the central region and USP Campus (both high and low, respectively). Other map showed a strong correlation between the POI index and trip index, especially in Itaim Bibi, Vila Olímpia, Av. Paulista, Av. Indianópolis, and downtown. However, R. Vergueiro showed a contrast, with a high POI index but low trip index, resulting in an overall correlation of 0.35.

## Conclusions
The POI index had the highest influence on bicycle trip volume, even with a sampled dataset. The system is well-integrated with various city regions in terms of bike lanes and transport modes, despite the city's infrastructure limitations. These analyses provide valuable insights for planning the expansion of bike-sharing systems in São Paulo.

## Acknowledgements
Thanks to CNPq, research advisor Professor Fabio Kon, Unesp, and USP.

## References
- KON, F.; FERREIRA, É. C.; DE SOUZA, H. A.; et al. Abstracting mobility flows from bike-sharing systems. Public Transport, v. 14, p. 545–581, 2022. DOI: [10.1007/s12469-020-00259-5](https://doi.org/10.1007/s12469-020-00259-5).
- LIMA, A. Y. F. de; KON, F. Impacts of the COVID-19 pandemic on the bicycle sharing system in São Paulo. Technical Report.
