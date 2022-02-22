# Development of influenza cases in Baden – Württemberg

## Introduction
Seasonal influenza is an infectious disease, transmitted via droplets, with increasing prevalence in Baden-Württemberg. The prevalent types are influenza A, B and C. 
Influenza A comes with several subtypes classified by their surface proteins hemagglutinin and neuraminidase. Influenza A subtypes are well 
known for causing pandemics (e.g., Spanish flu, swine flu). Influenza B is distinguished into two lineages:  B/Yamagata and B/Victoria. Influenza C 
is not observed in high case numbers and symptoms are mild, so extensive types/lineage analysis is not performed by the WHO. [1]
It was stated that the increase in prevalence was boosted from 2012 onwards, due to a sudden increase in strain diversity. Further the COVID restrictions 
from 2020 onwards were aimed to prevent the expected influenza waves, and might even have led to loss of some influenza strains. The COVID measurement 
mainly reduced the close-coming-together of people, which minimzied the spreading. [2, 3]  
***
## Research question and Hypotheses
This study aims to answer the question: whether the spreading of influenza differs between sparse and densely populated area and how virus types 
contribute to differences in the regional spreading as well as whether the increase in strain diversity aided the potentially increasing prevalence. This sums up to the 
following hypotheses:  

1.) There is a constant increase in prevalence, which is steeper from 2012 onwards with sudden decrease in 2020. 

2a.) The spreading in sparse populated regions differs from the spreading in densely populated regions. 

2b.) The pattern of arising of virus types is differing among the sparse and densely populated regions. 

3.) An increase in virus type diversity contributes to higher case numbers. 

The research question and hypotheses were based on the assumption, that the prevalence increased over time from start of the recording in season 2000/01 
until 2019/20. With contact restrictions, wearing masks and less public events due to the COVID pandemic, a sudden decrease in influenza cases is expected. 
Further the case numbers in 2009 will be outstandingly higher than in the previous and following years, due to the swine flu pandemic, whose pathogen belongs to the influenza A subtypes. As previously mentioned, a sudden increase in virus subtypes/lineages is expected to happen in 2012.
***

## Available data and Code maintenance
To answer the research questions, influenza case number recordings were obtained from the Robert Koch Institute (RKI), which is the central official entity for 
infectious diseases control and monitoring in Germany. Public data on case numbers on district level is available for all notifiable diseases and can be queried 
using the SURVSTAT@RKI2.0 tool [here](https://survstat.rki.de/Content/Query/Create.aspx)[4]. Public demographic and area data is provided by the statistische Landesamt Baden – Württemberg and was downloaded using the 
query available [here](https://www.statistik-bw.de/SRDB/?E=GS). [5] Since both data sources are subject to constant updates, the data underlying this analysis was provided in the data section 
[here](/data/). Further a geographical dataset (geojson) was required to present the analysis outcome on a map. The data was obtained from source 6 and provided 
in the data section [here](/data/). [6] 
Due to extensive pre-processing before and after merging of the influenza data and the demographic data, a “raw” dataset was written to file and is as well available [here](/data/). 
For reproducing the analysis on the same data basis this file can be used directly. The whole data processing, analysing and dashboard building routine was separated 
in two parts: The loading, processing and merging part (jupyter notebook), which results in the described “raw” file. Variable description for this file can be found in the codebook [here](/data/codebook.md). 
The analysis and the building of the dashboard were kept in one jupyter notebook, because an explorative approach was chosen, which resulted in fluent transitions 
between analysis and building the plots for the dashboard and the set up of the dashboard. The analysis was structured in two more or less separate sections being: 
analysis of total case numbers per year and analysis of circulating virus strains per year. Both of the parts were analysed on different levels: whole province 
Baden – Württemberg, districts (= gemeentes) and on a in between level created by grouping the districts into categories based on their population density.

## Chosen Methodology
The dataset containing the area and demopgraphic data was assumed to be the "simpler" dataset in that sense, that measurements/estimations are always carried out in the same way and that recordings are complete. However, the estimation method was adapted to a more accurate methodology, therefore the data before 2011 needed to be interpolated. The
latest population estimate for the year 2021 was not published at the moment of downloading, so an extrapolation for that year was required. Here, a simple linear curve fitting approach was applied. This approach is limited in that sense, that the urban areas experience a faster poulation increase and the rural areas a slower increase from about the years 2018 onwards. For more accurate results this should be considered, and might be adjusted in future data pre-processing. For the influenza dataset the data was treated as if all cases ever occured in the whole population would have been recorded. However, not everyone sees a GP, especially when having mild symptoms only, consequently resulting in an underestimation of case numbers. Lacking recordings might have happend for the time period 2016 to 2021. Further the differentiation laboratory diagnostic is conducted to a way lower extent than for COVID, so the first appearance of a virus type might be shifted to later years and not all subtypes and lineages are present in the dataset. Further the amount of given vaccine doses and the effectivness of these modulating the yearly case numbers were not taken into consideration.

As previously mentioned, the analysis followed an explorative approach, therefore several representation show the same information. For the infographic, (stacked) barplots were preferred over line plots, to prevent the impression that the case numbers were continously recorded. The data contains one data point per year/season only. If line charts were more convinient in terms of implementation, hover tool option was provided to get a better grip of the actual datapoints shown. Line was preferred over scatter and bubble, becasue the trend over time is better visible using a line. The calender representation (heatmap like plots) shall aid to get an easy overview on circulating virus types based on color code provided. The geographical representation can aid to explore the total number of cases or cases by a specific virus type for one district or region of interest. This representation as well provides more insight on neighboring regions and might reveal trends, which cannot be understand from the category data visualisation alone. 
***


## References
[1] https://www.who.int/news-room/fact-sheets/detail/influenza-(seasonal) 

[2] https://www.statnews.com/2021/06/02/pandemic-upside-flu-virus-became-less-diverse-simplifying-task-of-making-flu-shots/ 

[3] Koutsakos, M et al.: Influenza lineage extinction during the COVID-19 pandemic?, Nature Reviews Microbiology, 2021, https://www.nature.com/articles/s41579-021-00642-4#citeas 

[4] https://survstat.rki.de/Content/Query/Create.aspx

[5] https://www.statistik-bw.de/SRDB/?E=GS

[6] http://opendatalab.de/projects/geojson-utilities/
