# Generalized variable description for the influenza datasets
***
The variables described here are present in each of the datasets, which were obtained for one district of Baden - Württemberg. the informatio on which district is covered by 
the dataset is stored in the file name and meta data of the file. The meta data lines and header were skipped, english variable names were used.

| Variable name           | data type | possible values | analysis variable name  | meaning |
| ----------------------- | :-------: | :-------------: | :-----------------: | :------------: |
| Jahr                    | int | 1960 - 2020| year | year of measurements |
| Gemeindegebiet ha         | float | 0. - inf. | area \[ha] | area of district in ha |
| Bevölkerung insgesamt Anzahl  | float | 0. - inf. | population | estimated population size |
| Bevölkerungsdichte EW/km^2 | float | 0. - inf. | population_desity | population per square kilometer for current district|
| Bevölerungsdichte Landeswert | float | 0. - inf. | population_density_bw| population per square kilometer whole Baden - Württemberg|
