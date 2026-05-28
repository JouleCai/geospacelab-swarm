# Overview

## What is GeospaceLAB?
GeospaceLAB is an open-source Python package designed to facilitate data access, management, and visualization for space physics and space weather research. It provides a unified process that connects data providers and space physics researchers, allowing them to focus more on data interpretation and research results. GeospaceLAB has been applied in the study of Magnetosphere-ionosphere-thermosphere coupling and has received recognition in the scientific community, with 44 stars (until 20.5.2025) on GitHub and inclusion in the Python in Heliosphysics Community (PyHC) in 2022.

:::{attention} Resources for GeospaceLAB
- GeospaceLAB GitHub repository: [click here](https://github.com/JouleCai/geospacelab)
- GeospaceLAB Documentation: [click here](https://geospacelab.readthedocs.io/en/latest/) 
- GeospaceLAB PyPI package: [click here](https://pypi.org/project/geospacelab/)
- GeospaceLAB Swarm support documentation: [click here](https://geospacelab-swarm.readthedocs.io/en/latest/)
- GeospaceLAB Swarm support GitHub repository: [click here](https://github.com/JouleCai/geospacelab-swarm)
:::

## Supported Swarm data products in GeospaceLAB
rewrite: As listed in {numref}`tab:swarm-products`, GeospaceLAB currently supports 30 data products of Swarm mission. Those data products are selected from the categories of “Ionosphere/Magnetosphere”, “Thermosphere”, “Space Weather”, and “Magnetic measurements” in the [Swarm Product Data Handbook](https://swarmhandbook.earth.esa.int/catalogue/index). Users can easily access the listed Swarm data products from (1) ESA's [Swarm Dissemination Sever](https://earth.esa.int/eogateway/missions/swarm/data), (2) [Swarm VirES Service{sup}`*`](https://vires.services/), and (3) [VirES for Swarm - HAPI Server{sup}`*`](https://vires.services/hapi). The data access and visualization are tested and verified in GeospaceLAB.

:::{note}
`*`: For VirES and VirES HAPI services, only the MAG/LR data and its FAST data are currently supported. The support for other data products is under development and will be released in the future.
:::


:::{table} Supported Swarm data products in GeospaceLAB
:name: tab:swarm-products
| No.  | Product         | Level      | Folder                | Description                                                                | Status |
|------|-----------------|------------|-----------------------|----------------------------------------------------------------------------|--------|
| 1    | SW_AEJxLPL_2F   | 2          | Level2daily           | Auroral electrojets line profile – Line current method (LC)                | Tested |
| 2    | SW_AEJxLPS_2F   | 2          | Level2daily           | Auroral electrojets line profile – SECS method                             | Tested |
| 3    | SW_AEJxPBL_2F   | 2          | Level2daily           | Auroral electrojets peaks and boundaries from LC                           | Tested |
| 4    | SW_AEJxPBS_2F   | 2          | Level2daily           | Auroral electrojets peaks and boundaries from SECS                         | Tested |
| 5    | SW_AOBxFAC_2F   | 2          | Level2daily           | Auroral oval boundaries derived from FAC                                   | Tested |
| 6    | SW_DNSxACC_2_   | 2          | Level2daily           | Thermospheric density derived from ACC + POD                               | Tested |
| 7    | SW_DNSxPOD_2_   | 2          | Level2daily           | Thermospheric density derived from POD                                     | Tested |
| 8    | SW_EFIx_LP_1B   | 1          | Level1b               | Electric field instrument (EFI) Langmuir probe (LP) measurements at 2 Hz   | Tested |
| 9    | SW_EFIx_LP_FP   | Advanced   | Advanced/Plasma_Data  | EFI faceplate (FP) plasma density at 16 Hz                                 | Tested |
| 10   | SW_EFIx_LP_HM   | Advanced   | Advanced/Plasma_Data  | EFI LP extended at 2 Hz                                                    | Tested |
| 11   | SW_EFIx_TCT02   | Advanced   | Advanced/Plasma_Data  | Extended dataset of EFI TII cross-track ion flow measurements at 2 Hz      | Tested |
| 12   | SW_EFIx_TCT16   | Advanced   | Advanced/Plasma_Data  | Extended dataset of EFI TII cross-track ion flow measurements at 16 Hz     | Tested |
| 13   | SW_EFIxIDM_2_   | Advanced   | Advanced/Plasma_Data  | EFI LP ion drift and effective mass                                        | Tested |
| 14   | SW_EFIxLPI_1B   | 1b         | Level1b               | EFI LP measurements at 1 Hz                                                | Tested |
| 15   | SW_EFIxTIE_2_   | 2          | Level2daily           | Estimated ion temperatures along Swarm satellite orbits                    | Tested |
| 16   | SW_EFIxTMS_2F   | 2          | Level2daily           | Dayside equatorial electric field                                          | Tested |
| 17   | SW_FAC_LLS_2F   | 2          | Level2daily           | Field-aligned currents (dual-satellite A-C) least-squres                   | Tested |
| 18   | SW_FAC_TMS_2F   | 2          | Level2daily           | Field-aligned currents (dual-satellite A-C)                                | Tested |
| 19   | SW_FACxTMS_2F   | 2          | Level2daily           | Field-aligned currents (single satellite)                                  | Tested |
| 20   | SW_IBIxTMS_2F   | 2          | Level2daily           | Ionospheric bubble index                                                   | Tested |
| 21   | SW_IPDxIRR_2F   | 2          | Level2daily           | Ionospheric Plasma Irregularities characterised by Swarm (IPIR)            | Tested |
| 22   | SW_MAGx_HR_1B   | 1b         | Level1b               | Magnetic field (50 Hz) from VFM                                            | Tested |
| 23   | SW_MAGx_LR_1B   | 1b         | Level1b               | Magnetic field (1 Hz) from VFM and ASM                                     | Tested |
| 24   | SW_MITx_LP_2F   | 2          | Level2daily           | Midlatitude ionospheric trough boundries and minma drived from LP          | Tested |
| 25   | SW_MITxTEC_2F   | 2          | Level2daily           | Midlatitude ionospheric trough boundries and minma drived from TEC         | Tested |
| 26   | SW_NIX_TMS_2F   | 2          | Level2daily           | NIX                                                                        | Tested |
| 27   | SW_PPIxFAC_2F   | 2          | Level2daily           | Equatorward boundary of SSFACs and the associated midnight PP index        | Tested |
| 28   | SW_TECxTMS_2F   | 2          | Level2daily           | Ionospheric total electron content                                         | Tested |
| 29   | SW_TIX_TMS_2F   | 2          | Level2daily           | TIX                                                                        | Tested |
| 30   | SW_WHIxEVT_2_   | 2          | Level2daily           | Whistler events from ASM BM 250 Hz data                                    | Tested |
:::