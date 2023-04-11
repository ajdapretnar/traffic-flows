[![DOI](https://img.shields.io/badge/DOI-arXiv-red)](https://arxiv.org/abs/2111.15661)
[![DOI](https://img.shields.io/badge/DOI-figshare-orange)](https://doi.org/10.6084/m9.figshare.13259093)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ajdapretnar/traffic-flows/HEAD)

# Open Data and Quantitative Techniques for Anthropology of Road Traffic
by Ajda Pretnar Žagar, Tomaž Hočevar and Tomaž Curk

Jupyter notebook scripts, Orange workflows, and data that support the findings of the study titled "*Open Data and Quantitative Techniques for Anthropology of Road Traffic*" and submitted for review.

#### Data

The traffic data comes from an extensive network of road traffic counters of the Slovenian Infrastructure Agency. Both real-time data and historical data are publicly
available for different locations, directions of traffic and lanes. We analyzed the historical data for 2015, 2016, and 2017, for which traffic counts were available at hourly intervals. We preprocessed and aggregated the data in different ways (per month, season, or day of the week) for the purposes of traffic analysis. Some aggregations are provided as *csv* files in this repository and used in the following Jupyter notebooks and Orange workflows. Most of the examples use `cars-pivot.csv` as the input data. It stores hourly profiles of traffic grouped by the counter location, direction of traffic and month.

### Jupyter notebooks

The included notebooks present examples of handling and visualizing traffic count data. Run the notebook with `jupyter notebook Notebook_Name.ipynb`. The notebooks are independent and can be run in any order.

Requirements: `Python`, `Jupyter`, `Pandas`, `matplotlib` (`folium` and `branca` for map visualizations). The provided notebooks should run using any recent version of Python (e.g. Python 3.10.0) and other required packages. See `requirements.txt` for a set of specific version that can be used.

- [Absolute and relative difference.ipynb](https://github.com/ajdapretnar/traffic-flows/blob/master/Absolute%20and%20relative%20difference.ipynb): Presents the concept of baseline traffic and the measure of absolute and relative deviation from it.
- [Basic Sorting.ipynb](https://github.com/ajdapretnar/traffic-flows/blob/master/Basic%20Sorting.ipynb): Basic manipulation and visualization of traffic count data. (see Figure 1b)
- [Traffic profile deviations.ipynb](https://github.com/ajdapretnar/traffic-flows/blob/master/Traffic%20profile%20deviations.ipynb): Other measures of traffic profile deviation.
- [Maps.ipynb](https://github.com/ajdapretnar/traffic-flows/blob/master/Maps.ipynb): Example visualization of motorbike traffic on Slovenian road network (analogous to Figure 3b).

An example from notebook [Maps.ipynb](https://github.com/ajdapretnar/traffic-flows/blob/master/Maps.ipynb) displaying the amount of motorbike traffic on a map where we can observe a larger amount of motorbikes in the western part of the country.

![Motorbikes](motorbikes-map.png)

### Orange workflows

Open the workflows with `orange-canvas Workflow_Name.ows`. Workflows include instructions for setting up individual widgets correctly.

Requirements: [Orange3](https://orangedatamining.com/download/), (`Orange3-Geo` add-on for map visualizations). You can use Orange3 version 3.34.0 or any other recent version of Orange.

- [coefficient-of-variation.ows](https://github.com/ajdapretnar/traffic-flows/blob/master/coefficient-of-variation.ows): Computation of one measure for detecting traffic counters with deviating profiles and visualization of the monthly traffic profile of one such traffic counter (Vršič mountain pass).
- [counters-clustering.ows](https://github.com/ajdapretnar/traffic-flows/blob/master/counters-clustering.ows): Clustering counters by their traffic profiles and visualization of counter locations on a map (see Figure 7).
- [counters-yearly-averages.ows](https://github.com/ajdapretnar/traffic-flows/blob/master/counters-yearly-averages.ows): Seasonal traffic profile by years in Slovenia (see Figure 2a) 
- [sum-of-mean.ows](https://github.com/ajdapretnar/traffic-flows/blob/master/sum-of-mean.ows): Similar to `coefficient-of-variation.ows` with a different deviation measure and observing the traffic counter on the road from Rogla to Zreče (see Figure 1a).
- [z-score.ows](https://github.com/ajdapretnar/traffic-flows/blob/master/z-score.ows): Detection of counters with daily peaks using the z-score measure (see Figure 5).



Screenshot of the workflow `counters-clustering.ows` and the Line Plot widget showing the average profiles in the six clusters of traffic profiles.

![Counters clustering](counters-clustering.png)

![Counters clustering](line-plot.png)
