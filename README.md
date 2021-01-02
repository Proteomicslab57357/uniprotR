# UniprotR: Retrieving and visualizing protein sequence and functional information from Universal Protein Resource (UniProtknowledgebase)

[![CRAN RStudio mirror downloads](https://cranlogs.r-pkg.org/badges/grand-total/UniprotR?color=blue)](https://CRAN.R-project.org/package=UniprotR) 
[![CRAN RStudio mirror downloads](https://cranlogs.r-pkg.org/badges/UniprotR)](https://CRAN.R-project.org/package=UniprotR) 
[![](https://www.r-pkg.org/badges/version/UniprotR?color=green)](https://CRAN.R-project.org/package=UniprotR) 
[![](https://img.shields.io/badge/doi-https%3A%2F%2Fdoi.org%2F10.1016%2Fj.jprot.2019.103613-red)](https://doi.org/10.1016/j.jprot.2019.103613)
[![](https://badgen.net/badge/Citations/4/:color?icon=github)](https://doi.org/10.1016/j.jprot.2019.103613)



![](https://i.ibb.co/jDS7Khq/pinterest-profile-image.png)

# Installation
The package is avilable now online at https://proteomicslab57357.shinyapps.io/UniprotR/

```R
install.packages("UniprotR")
```

# Description

Connect to [Uniprot](https://www.uniprot.org/) to retrieve information about proteins using their accession 
number such information could be name or taxonomy information,The package provides a powerful data retrieval capabilities in addition to screening visualization tool, and ID conversion tool that helps researchers for analyzing their proteomics data as well as subsequent downstream analysis.

# Documentation

For the documentation see: [UniprotR Documentation](https://cran.r-project.org/web/packages/UniprotR/UniprotR.pdf).

# Package information

- Version: **v2.0.1**
- License: GPL-3
- Encoding: UTF-8
- Imports: 	utils , grDevices , stats , grid , graphics , httr , plyr , dplyr , scales , magrittr , magick , data.tree , ggplot2 , tidyverse , gridExtra , ggpubr , alakazam, curl, networkD3, stringr , qdapRegex , htmlwidgets, ReactomePA , gprofiler2
- NeedsCompilation: no
- Repository: CRAN
- link to package on CRAN: [UniprotR](https://cran.r-project.org/package=UniprotR)


# Usage

**Example**

```R
library(UniprotR) 
#Read Accessions from csv file , Note : Accessions must be in the first column. 
Accessions <-GetAccessionList("https://s3.amazonaws.com/csvpastebin/uploads/9571fa356c67a0c7c95e8431799a051a/Accessions.csv") 
#Get Taxanomy Information 
TaxaObj <- GetNamesTaxa(Accessions) 
#Visualize Chromosomes localization
PlotChromosomeInfo(TaxaObj)
#Visualize protein's gene name as Network 
PlotGenesNetwork(TaxaObj)
```

**Gene ontology of protein list**
```R
#Get Gene ontolgy Information 
GeneOntologyObj <- GetProteinGOInfo(Accessions) 
#Plot Biological process information top 10 go terms  
PlotGOBiological(GeneOntologyObj, Top = 10) 
#Plot molecular function information top 20 go terms
Plot.GOMolecular(GeneOntologyObj, Top = 20)
#Plot subcellualr localization information 
Plot.GOSubCellular(GeneOntologyObj) 
#Combine Gene ontology plots into one plot 
PlotGoInfo(GeneOntologyObj)
```

**Enrichment analysis using KEGG, Reactome of protein list**
```R
Enrichment.gprofiler(Accessions)
```

**Get diseases associated with protein list**
```R
PathologyObj <- GetPathology_Biotech(Accessions)
Diseases <- Get.diseases(PathologyObj)
```

**Protein- Protein interaction using STRING**
```R
#Get Protein-Protein Interaction within input data 
#Path example = "E:/Users/Network.pdf"
GetproteinNetwork(Accessions , Path to save your pdf file) 
```
# Contribution Guidelines

For bugs and suggestions, the most effective way is by raising an issue on the github issue tracker. Github allows you to classify your issues so that we know if it is a bug report, feature request or feedback to the authors.

**Email: Proteomicslab2017@gmail.com**

# Future plans

- Add pathway analysis workflow that connects to KEGG and reactome.
# Citation

Soudy, Mohamed, Ali Mostafa Anwar, Eman Ali Ahmed, Aya Osama, Shahd Ezzeldin, Sebaey Mahgoub, and Sameh Magdeldin. 2020. “UniprotR: Retrieving and Visualizing Protein Sequence and Functional Information from Universal Protein Resource (UniProt Knowledgebase).” Journal of Proteomics 213 (February). Elsevier B.V. doi:10.1016/j.jprot.2019.103613.


![](https://github.com/Proteomicslab57357/UniprotR/blob/master/logos/CCHF_57357.png)
