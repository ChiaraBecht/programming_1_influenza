# programming1 Studying influenza cases in Baden-Württemberg
* * *

![PIXNIO-169857-636x544](https://user-images.githubusercontent.com/94694457/155092715-61d903c5-d96f-4170-8f79-82f02a16467d.jpg) by: <a href="https://pixnio.com/de/wissenschaft/mikroskopische-aufnahmen/grippe/mitglied-taxonomische-familie-orthomyxoviridae-grippe-virus-ein-mehr-organismus">Erskine. L. Palmer, Ph.D., M. L. Martin, USCDCP</a> auf <a href="https://pixnio.com/de/">Pixnio</a>


## Description
* * *
This repository contains the code to run a dashboard, which retrospectively monitors the influenza cases numbers and the virus type circulation in Baden - Württemberg. 

### Data
Influenza case number data was obtained from the Robert Koch Institute using the tool SURVSTAT@RKI2.0 (https://survstat.rki.de/Content/Query/Create.aspx). The data is constantly appended, therfore the data on which this analysis was based can be found [here](/data/RKI/)

The district related data (area size, population size, etc.) was obtained from the statistische Landesamt Baden - Württemberg using their Query tool (https://www.statistik-bw.de/SRDB/?E=GS). For the same reasons as for the influenza data, the used data can be found [here](/data/Stat_Landesamt_BW/)

Geographical data on district level was required to produce a geographical representation. The required geojson file was obtained form (http://opendatalab.de/projects/geojson-utilities/). The data can be found [here](/data/geodata)

A merged dataset was produced with additional columns, which can be found [here](/data/)


### Data description

The different columns of the merged dataset are described [here](/data/codebook.md)

## Installation
* * *

### Single install
The easiest way to install all the required packages is via conda. How to install conda on your system can be found [here](https://docs.anaconda.com/anaconda/install/index.html).

To create a new environment which contains all the required packages plus the right version run the following code:

```bash
  conda env create -f environment.yml
```

This will create a new environment named `mosquito_env` which can be used to run this repository.

> NOTE: the environment.yml is located in the install/ directory [here](install/environment.yml).

### Multiple installs
An other option is to install each package seperately, either with conda or pip.

conda:
```bash
  conda install <PACKAGE>=<VERSION>
```

pip
```bash
  pip install <PACKAGE>==<VERSION>
```

> NOTE: make sure to use the correct versions, which are listed [here](#packages).

## Getting started
* * *
To open the dashboard run the [Final_assignment_Data_Analysis.ipynb](analysis/Final_assignment_Data_Analysis.ipynb) notebook from top to bottom.


## Requirements
* * *
| Software                          | Version  |
| --------------------------------- | :------: |
| [Python](https://www.python.org/) | `3.9.7`  |    


## Packages
* * *
| Package                                              | Version  |
| ---------------------------------------------------- | :------: |
| [numpy](https://numpy.org/)                          | `1.21.2` |
| [pandas](https://pandas.pydata.org/)                 | `1.3.3`  |
| [bokeh](https://bokeh.org/)                          | `2.3.3`  |
| [folium](https://python-visualization.github.io/folium/) | `0.12.1.post1` |
| [panel](https://panel.holoviz.org/)                  | `0.12.1` |
| [holoviews](https://holoviews.org/)                  | `1.14.6` |
| [hvplot](https://hvplot.holoviz.org/)                | `0.7.3`  |
| [scipy](https://scipy.org/)                          | `1.7.1`  |
| [jupyter](https://jupyter.org/)                      | `1.0.0`  |
| [statsmodel](https://www.statsmodels.org/)           | `0.12.2` |
| [pathlib](https://pathlib.readthedocs.io/en/pep428/) | `1.0.1`  |
| [os](https://docs.python.org/3/library/os.html)      | `3.10.2` |
| [re](https://docs.python.org/3/library/re.html)      | `3.10.2` |
| [param](http://param.holoviz.org/)                   | `1.12.0` |



## License
* * * 
This project contains a MIT [license](./LICENSE.md)


