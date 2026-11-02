Contrasting Spatial Routes to Denser Settlement in Three Prehispanic Regional Sequences of Colombia (under review)
--------------------------------------------------------------

This repository contains code and data for a multidimensional spatial analysis framework designed to compare regional settlement patterns in early complex societies. The protocol integrates (1) area-weighted kernel density estimation for the concentration of occupation, (2) nearest-neighbor statistics and L functions for spacing and clustering, (3) Approximate Bayesian Computation for comparing candidate spatial processes, (4) proximity graphs for connectivity, (5) rank-size coefficients and Cliff's delta for site-size structure, (6) regional population density estimates, and (7) Random Forest classification. Every statistic is judged against patterns simulated with the same number of sites in the same survey area. The protocol is applied comparatively to three pre-Hispanic sequences in Colombia, Río Frío (Sierra Nevada de Santa Marta), Filandia (Middle Cauca), and the Sabana de Bogotá.

Repository Structure:
----------------------------------
1. GIS:
   - Contains the spatial data files (shapefile components) defining the survey boundaries and settlement distributions. The R code reads these files from a local copy of this repository:
     • Rio_Frio_Limite_Survey (Survey boundary)
     • Rio_Frio_Sitios_Neguanje, Rio_Frio_Sitios_Buritaca, Rio_Frio_Sitios_Tairona (Periods: Neguanje, Buritaca, Tairona)
     • Filandia_Limite_Survey (Survey boundary)
     • Filandia_Sitios_Periodo_Temprano, Filandia_Sitios_Periodo_Medio, Filandia_Sitios_Periodo_Tardio (Periods: Early, Middle, Late)
     • Bogota_Limite_Survey (Survey boundary)
     • Bogota_Sitios_Early_Herrera, Bogota_Sitios_Late_Herrera, Bogota_Sitios_Muisca (Periods: Early Herrera, Late Herrera, Muisca)
     • Corrected layers of Filandia_Sitios_Periodo_Medio, Filandia_Sitios_Periodo_Tardio, Filandia_Limite_Survey, and Bogota_Limite_Survey, whose file names end in 20261029_094301
   - All layers use WGS 84 / UTM zone 18N (EPSG 32618). Site layers record each site's identifier (Site_ID) and area in hectares (Size_HA).
   - The Filandia and Sabana de Bogotá layers derive from Jaramillo et al. (2023) and Boada Rivas (2025) and are also distributed by the Comparative Archaeology Database of the University of Pittsburgh. The Río Frío layers come from the Río Frío Basin Regional Archaeology Program (Soto Rodríguez 2026).

2. R Code Files:
   - The main R Markdown notebook (AA_SIGNATURES_CHIEFDOMS) contains the code to:
     a) Load required packages and configure the environment.
     b) Read the GIS files and verify their coordinate system, site counts, identifiers, geometry, and containment within each survey boundary.
     c) Perform the spatial pattern, model comparison, network, site-size, demographic, and classification analyses.
     d) Generate Figures 2 through 8 and Tables 1 through 3 as presented in the manuscript, each figure followed by a numeric summary of the values it displays.

Software and Key Package Versions:
----------------------------------
- R version: 4.6.1

Key R packages used in this project include:
    • abc: version 2.2.2
    • caret: version 7.0-1
    • dplyr: version 1.2.1
    • future: version 1.75.0
    • future.apply: version 1.20.2
    • ggplot2: version 4.0.3
    • ggspatial: version 1.1.11
    • igraph: version 2.3.3
    • knitr: version 1.52
    • patchwork: version 1.3.2
    • randomForest: version 4.7-1.2
    • rmarkdown: version 2.32
    • scales: version 1.4.0
    • sf: version 1.1-3
    • spatstat.explore: version 3.8-2
    • spatstat.geom: version 3.8-2
    • spatstat.model: version 3.7-2
    • spatstat.random: version 3.5-1
    • spdep: version 1.4-2
    • tibble: version 3.3.1
    • tidyr: version 1.3.2

Getting Started:
----------------------------------
1. Clone or download this repository, or download only AA_SIGNATURES_CHIEFDOMS.Rmd.
2. Open AA_SIGNATURES_CHIEFDOMS.Rmd in RStudio. An active Internet connection is required, because the notebook downloads the RData files directly from the RData folder of this repository. To read a local copy instead, set RDATA_DIR in the Configuration section to the path of the local RData folder.
3. In the Configuration section, set FAST_MODE to TRUE for a quick test with fewer simulations. No other setting needs to be changed.
4. Render the notebook from the R console with rmarkdown::render("AA_SIGNATURES_CHIEFDOMS.Rmd", envir = globalenv()) to reproduce all figures and tables. Apart from the rendered report and temporary copies of the RData files, which are deleted after reading, the notebook writes no files, and the figures, tables, and numeric summaries remain in the R session.

Manuscript Summary:
----------------------------------
Regional settlement data are often read as evidence that demographic growth brings settlement hierarchy. This study examines that expectation in three full-coverage surveys in Colombia, Río Frío in the Sierra Nevada de Santa Marta, Filandia in the Middle Cauca, and the Sabana de Bogotá, which hold 2,812 site records in nine period layers between about 400 BC and AD 1600. Site density roughly tripled in every sequence, yet the regions diverged. Sites in Río Frío and the Sabana de Bogotá stood closer together than random placement predicts, and Bogotá gathered its occupied area into a few dense foci, whereas spacing in Filandia did not depart from randomness. Rank-size distributions stayed convex in all nine layers, only four of 23 apparent network effects survived changes in graph construction, and none of the candidate point processes passed all four validation checks. Population density grew faster than site density where it could be estimated. These dimensions did not change together in any sequence, consistent with multilineal accounts of complexification.

For questions or further information, please contact: lms313@pitt.edu
