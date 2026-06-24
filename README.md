# code_TransAlbedo_HK

[![DOI](https://zenodo.org/badge/1276067909.svg)](https://zenodo.org/doi/10.5281/zenodo.20828141)

## Introduction

This repository is supplementary to the paper "Sun, Y., Fu, W., Schultz, D. M., He, C., Tai, A. P. K., Tam, C. Y., & Zheng, Z. (2026). Future atmospheric and urban responses to phased deployment of white roofs in Hong Kong, China."

The objectives of this project are:

- Propose a new evaluation method to specify the implementation pathway using the [transient roof albedo representation](https://doi.org/10.1029/2024MS004380) and [WRF-CLMU](https://doi.org/10.31223/X5MT9P) functionalities;
- Mimic urban adaptive action that increases roof albedo in Hong Kong by 0.025 per month from April to September of 2035-2039 for five years;
- Examine the albedo-induced changes in local climate (urban and rural) and atmosphere.

## Scripts and data

### [1_code_modification](./1_code_modification)

This study uses [WRFv4.7.1](https://github.com/wrf-model/WRF/tree/release-v4.7.1) and [CTSM5.3.024](https://github.com/ESCOMP/CTSM/tree/ctsm5.3.024) in a coupled mode. Files listed below are for CTSM modification:

- [bld/CLMBuildNamelist.pm](./1_code_modification/bld/CLMBuildNamelist.pm)
- [bld/namelist_files/namelist_defaults_ctsm.xml](./1_code_modification/bld/namelist_files/namelist_defaults_ctsm.xml)

- [bld/namelist_files/namelist_definition_ctsm.xml](./1_code_modification/bld/namelist_files/namelist_definition_ctsm.xml)
- [src/biogeophys/UrbanAlbedoMod.F90](./1_code_modification/src/biogeophys/UrbanAlbedoMod.F90)
- [src/biogeophys/UrbanParamsType.F90](./1_code_modification/src/biogeophys/UrbanParamsType.F90)
- [src/cpl/lilac/lnd_comp_esmf.F90](./1_code_modification/src/cpl/lilac/lnd_comp_esmf.F90)
- [src/cpl/share_esmf/UrbanDynAlbMod.F90](./1_code_modification/src/cpl/share_esmf/UrbanDynAlbMod.F90)
- [src/cpl/utils/lnd_import_export_utils.F90](./1_code_modification/src/cpl/utils/lnd_import_export_utils.F90)
- [src/main/clm_driver.F90](./1_code_modification/src/main/clm_driver.F90)
- [src/main/clm_instMod.F90](./1_code_modification/src/main/clm_instMod.F90)
- [tools/contrib/create_scrip_file.ncl](./1_code_modification/tools/contrib/create_scrip_file.ncl)

### [2_illustration](./2_illustration)

The figures listed below illustrate previous literature and white roof mechanisms.

| Subject                                                      | Visualization                                    |
| ------------------------------------------------------------ | ------------------------------------------------ |
| Numerical simulations for white roof assessment              | [Figure](./2_illustration/literature_review.pdf) |
| Map WRF simulations in journal articles published in 2011-2025 | [Figure](./2_illustration/wrf-high-albedo.pdf)   |
| Illustration of urban and atmospheric responses to white roofs | [Figure](./2_illustration/cooling_effect.pdf)    |

### [3_simulation_output_analysis](./3_simulation_output_analysis)

The scripts listed below process output from CNTL (`transient_urbanalbedo_roof=.false.`) and TranAlbe (`transient_urbanalbedo_roof=.true.`) simulations and visualize them.

| Num. | Subject                                                      | Output data process                                          | Visualization                                                |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 3.1  | [Urban fraction and roof albedo](./3_simulation_output_analysis/3.1_urban_fraction_roof_albedo/) | Use [Export.ipynb](./3_simulation_output_analysis/3.1_urban_fraction_roof_albedo/Export.ipynb) to export surface input data | [Figure.ipynb](./3_simulation_output_analysis/3.1_urban_fraction_roof_albedo/Figure.ipynb) |
| 3.2  | [Model domains](./3_simulation_output_analysis/3.2_model_domains/) | Not applicable                                               | [Figure.ipynb](./3_simulation_output_analysis/3.2_model_domains/Figure.ipynb) |
| 3.3  | [Baseline results](./3_simulation_output_analysis/3.3_baseline_results) | Use [Export.ipynb](././3_simulation_output_analysis/3.3_baseline_results/Export.ipynb) to export results in the CNTL simulation | [Figure.ipynb](./3_simulation_output_analysis/3.3_baseline_results/Figure.ipynb) |
| 3.4  | [Heatwave metrics](./3_simulation_output_analysis/3.4_heatwave_metrics) | Use [Export.ipynb](./3_simulation_output_analysis/3.4_heatwave_metrics/Export.ipynb) to export heatwave metrics in the CNTL and TranAlbe simulations | Not applicable                                               |
| 3.5  | [Human heat stress metrics](./3_simulation_output_analysis/3.5_human_heat_stress_metrics) | Use [Export.ipynb](./3_simulation_output_analysis/3.5_human_heat_stress_metrics/Export.ipynb) to export human heat stress metrics in the CNTL and TranAlbe simulations | [Figure.ipynb](./3_simulation_output_analysis/3.5_human_heat_stress_metrics/Figure.ipynb) |
| 3.6  | [Building energy metrics](./3_simulation_output_analysis/3.6_building_energy) | Use [Export.ipynb](./3_simulation_output_analysis/3.6_building_energy/Export.ipynb) to export air-conditioning and space heating fluxes in the CNTL and TranAlbe simulations | [Figure.ipynb](./3_simulation_output_analysis/3.6_building_energy/Figure.ipynb) |
| 3.7  | [Anthropogenic heat](./3_simulation_output_analysis/3.7_anthropogenic_heat/) | Use [Export.ipynb](./3_simulation_output_analysis/3.7_anthropogenic_heat/Export.ipynb) to export anthropogenic heat fluxes in the CNTL and TranAlbe simulations | Not applicable                                               |
| 3.8  | [Meteorological variations](./3_simulation_output_analysis/3.8_meteorological_variations) | Use [Export.ipynb](./3_simulation_output_analysis/3.8_meteorological_variations/Export.ipynb) to export changes in meteorological variables between the CNTL and TranAlbe simulations | [Figure.ipynb](./3_simulation_output_analysis/3.8_meteorological_variations/Figure.ipynb) |
| 3.9  | [Cloud fractions](./3_simulation_output_analysis/3.9_cloud_fractions) | Use [Export.ipynb](./3_simulation_output_analysis/3.9_cloud_fractions/Export.ipynb) to export changes in cloud fraction between the CNTL and TranAlbe simulations | [Figure.ipynb](./3_simulation_output_analysis/3.9_cloud_fractions/Figure.ipynb) |
| 3.10 | [Urban heat island](./3_simulation_output_analysis/3.10_urban_heat_island/) | Use [Export.ipynb](./3_simulation_output_analysis/3.10_urban_heat_island/Export.ipynb) to export changes in urban heat island intensity between the CNTL and TranAlbe simulations | [Figure.ipynb](./3_simulation_output_analysis/3.10_urban_heat_island/Figure.ipynb) |
| 3.11 | [Urban and rural temperatures](./3_simulation_output_analysis/3.11_urban_rural_temperatures/) | Use [Export.ipynb](./3_simulation_output_analysis/3.11_urban_rural_temperatures/Export.ipynb) to export changes in urban/rural ground and canopy-air temperatures between the CNTL and TranAlbe simulations | [Figure.ipynb](./3_simulation_output_analysis/3.11_urban_rural_temperatures/Figure.ipynb) |
| 3.12 | [Regression](./3_simulation_output_analysis/3.12_regression) | Use [Export.ipynb](./3_simulation_output_analysis/3.12_regression/Export.ipynb) to conduct regressions | Not applicable                                               |
| 3.13 | [Morphological impact](./3_simulation_output_analysis/3.13_morphological_impact) | Use [Export.ipynb](./3_simulation_output_analysis/3.13_morphological_impact/Export.ipynb) to export morphological parameters and temperature reduction | [Figure.ipynb](./3_simulation_output_analysis/3.13_morphological_impact/Figure.ipynb) |

### [4_auxiliary_dataset](./4_auxiliary_dataset)

The auxiliary datasets used for analysis are listed below.

| Num. | Dataset name                                                 | Source                                                       |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 4.1  | [Administrative shapefile](./4_auxiliary_dataset/4.1_HK_shapefile) | [Link](https://opendata.esrichina.hk/datasets/esrihk::hong-kong-18-districts/about) |
| 4.2  | [Land mask](./4_auxiliary_dataset/4.2_land_mask)             | Not applicable                                               |
| 4.3  | [Annual journal publications of WRF simulations with high urban albedo](./4_auxiliary_dataset/4.3_WRF_literature_review/) | Not applicable                                               |
| 4.4  | [Köppen-Geiger climate zone](./4_auxiliary_dataset/4.4_koppen_geiger_climate_zone) | [Link](https://doi.org/10.6084/m9.figshare.21789074)         |

- [WRF_high_urban_albedo_2011-2025](./4_auxiliary_dataset/4.3_WRF_literature_review/WRF_high_urban_albedo_2011-2025.xlsx) lists previous publications (2011-2025) on WRF simulations with high urban albedo. 

## Acknowledgments

- This work was supported by the Natural Environment Research Council [grant number UKRI1294].
- The authors appreciate the joint research funding from The University of Manchester and The Chinese University of Hong Kong.
- This work used the [ARCHER2 UK National Supercomputing Service](https://www.archer2.ac.uk/) and [JASMIN, the UK’s collaborative data analysis environment](https://www.jasmin.ac.uk/). 
- Z.Z. appreciates the support provided by the academic start-up funds from the Department of Earth and Environmental Sciences at The University of Manchester. 
- Y.S. is supported by Z.Z.'s academic start-up funds.
- The authors declare no conflict of interest.
