# GSMA Reported Cellular Data Coverage in Africa

This map presents the geographic extent of reported 2G, 3G, and 4G mobile network coverage in Africa across the 2012 through 2018 releases of the GSMA Mobile Coverage Explorer data. The purpose of the figure is to illustrate the spatial and temporal coverage of the available source data and to highlight differences across technologies and annual releases.

[View or download the full-resolution PDF](gsma_reported_africa_cellular_coverage_2012_2018.pdf)

## Data sources and credit

The underlying cellular coverage data were obtained through [Stanford EarthWorks](https://earthworks.stanford.edu/), Stanford University Libraries' geospatial data discovery platform. The available GSMA Mobile Coverage Explorer records can be found through the following catalog search:

[Browse GSMA datasets in Stanford EarthWorks](https://earthworks.stanford.edu/?q=gsma&search_field=all_fields&sort=gbl_indexYear_im+desc%2C+dct_title_sort+asc)

The coverage products were published as annual Mobile Coverage Explorer releases. According to the associated metadata, the coverage information was sourced from network operators through [GSMA](https://www.gsma.com/) and [Collins Bartholomew](https://www.collinsbartholomew.com/). The source datasets represent operator-reported network coverage rather than independently measured signal observations, subscriber locations, mobile phone use, or new coverage added during a particular year.

Country boundaries used to define the African study area were derived from the [Esri World Countries](https://hub.arcgis.com/datasets/esri::world-countries/) dataset.

## Interpretation

Each panel represents the coverage included in a particular annual GSMA release. The release year generally reflects operator information received through approximately the end of the preceding calendar year. For example, the release labeled 2016 includes operator data received through approximately the end of 2015.

The source rasters classify covered locations using the following values:

- `1`: strong signal strength
- `2`: variable signal strength

Both classes were combined into a single mapped coverage category for this figure. Consequently, the map shows areas classified as having either strong or variable signal. It does not distinguish between the two signal classes.

The annual layers are snapshots of coverage reported in each release. They do not represent only the coverage added during that year. They should also not be interpreted as direct measurements of cellular use, subscriber adoption, network speed, or signal quality experienced by individual users.

## Important data limitations

The source metadata state that not every network operator submitted coverage information. As a result, gaps in the maps and differences between annual releases may reflect changes in operator participation, data submission, or product construction, in addition to actual changes in network coverage.

An area without mapped coverage therefore does not necessarily indicate that cellular service was unavailable. Similarly, a large increase or decrease between releases should not automatically be interpreted as an equivalent physical expansion or contraction of network infrastructure.

One particularly visible example is the broad 4G footprint in the 2016 release, followed by substantially less mapped 4G coverage in the 2017 release. This pattern is also visible in the original GSMA maps available through Stanford EarthWorks. It is retained in this figure as a feature of the published source data and has not been adjusted to impose continuous or monotonically increasing coverage.

## Spatial processing

The original releases included a mixture of vector and raster formats. They were harmonized in ArcGIS Pro to create a common analysis-ready series.

Processing included:

- Selecting one source representation for each technology and release year
- Confirming and correcting coordinate-system metadata where necessary
- Projecting the data to Africa Albers Equal Area Conic
- Aligning all outputs to a common 1 km equal-area grid
- Using nearest-neighbor resampling for categorical raster values
- Combining strong and variable signal classes into one mapped coverage category
- Assigning `1` to mapped coverage and `0` to locations without mapped coverage inside the study area
- Retaining NoData outside the African study boundary
- Applying a consistent African land mask to all releases

The resulting mapped variable is:

- `1`: strong or variable coverage mapped in that release
- `0`: no coverage mapped in that release within the African study area
- `NoData`: outside the African study area

Because the source submissions may be incomplete, zero should be understood as **no coverage mapped in the release**, not necessarily as confirmed absence of cellular service.

## Temporal coverage

The complete cleaned collection includes:

- 2G releases from 2007 through 2018
- 3G releases from 2007 through 2018
- 4G releases from 2012 through 2018

The figure displays 2012 through 2018 because this is the common period for all three technologies. The available 2G and 3G releases from 2007 through 2011 were omitted from the figure for formatting purposes.

## Suggested citation

**Map and data processing**

Masterson, Scott. “GSMA Reported Cellular Data Coverage in Africa.” Map created from GSMA Mobile Coverage Explorer data distributed through Stanford EarthWorks, 2026.

**Underlying data**

GSMA and Collins Bartholomew. *Mobile Coverage Explorer* annual releases. Distributed through Stanford EarthWorks, Stanford University Libraries.  
[https://earthworks.stanford.edu/?q=gsma&search_field=all_fields&sort=gbl_indexYear_im+desc%2C+dct_title_sort+asc](https://earthworks.stanford.edu/?q=gsma&search_field=all_fields&sort=gbl_indexYear_im+desc%2C+dct_title_sort+asc)

Users should consult the individual Stanford EarthWorks records for release-specific metadata, access conditions, rights statements, and preferred citations.

## Rights and reuse

This repository presents a derived cartographic visualization. Copyright and other rights in the underlying Mobile Coverage Explorer datasets remain with their respective publishers and rights holders. Publication of this map does not grant permission to redistribute the original source datasets.

Users interested in accessing the underlying data should use the individual records available through [Stanford EarthWorks](https://earthworks.stanford.edu/?q=gsma&search_field=all_fields&sort=gbl_indexYear_im+desc%2C+dct_title_sort+asc) and comply with the access and reuse conditions listed there.

## Author

Created and processed by **Scott Masterson** using ArcGIS Pro.

This project is an independent research and cartographic product. It should not be interpreted as an official publication or endorsement by GSMA, Collins Bartholomew, Stanford University, Stanford University Libraries, or Esri.
