## Exploratory and Differential Expression Analysis of RNA-seq Data 

This repository contains tools for exploratory and differential expression analysis of RNA-seq data using DESeq2 package.

[Click here](https://github.com/nshanian/Documents/blob/main/DESeq2.html) for the HTML version of this workflow with the output and the embedded plots.

The RNA-seq data used in this workflow was generated as part of a study that investigated the regulatory role of short-chain fatty acids (SCFAs) propionate and butyrate in the context of colorectal cancer (CRC). Briefly, epigeneomic and transcriptomic profiles were compared in SCFA-treated and untreated CRC cells, normal cells and in mouse intestines, with the goal of gaining insight into changes in accessibility and expression of CRC-relevant genes. 

Once the initial steps of alignment and quantitation of transcript abundances have been completed, and a counts matrix is generated as described in the last step of `STAR_RSEM.sh` workflow in the `RNA-seq` repository, further downstream statistical analysis can be performed in R.

The DESeq2 Rmd workflow will identify differentially expressed genes between treated and untreated conditions. It will perform quality control assessment of replicates within each condition and between two conditions. The analysis is performed on raw data in `genes.results` format generated by using `rsem-generate-data-matrix` function in `rsem`, whereby counts data from each replicate and condition are concatenated into a data matrix in a Comma-separated values `.csv` format. 

To load the required files into the DESeq2 workflow, they will first have to be converted to Tab Delimited Text `.txt` format. This can be done by opening them in MS Excel and saving them as `.txt` files. If there are blank cells, they will have to be removed. Cells containing non-integer values with decimal places will have to be rounded off. A script detailing steps on how to do this in R is provided in this repository. 

In addition to the `counts_final.txt` file, the workflow also requires a metadata file that details the replicate and condition information. This will be used to establish the relationship between the factors and covariates in this experiment for the differential expression analysis. This information is in the `convariates.txt` file, which is also the study design and metadata file.  

Once the data matrix and metadata file are ready to be loaded into R, `BiocManager`, `pheatmap`, `ggplot2`, `DESeq2`, `EnhancedVolcano` packages will first have to be installed.  

Once all the required files have been prepared and the dependencies installed, _DESeq2_ will be used to identify differentially expressed genes.

For documentation and further information on each package used in the workflow as well as the topics covered see the references below:

[Modern Statistics for Modern Bioloy](https://web.stanford.edu/class/bios221/book/index.html)

[Bioconductor](https://bioconductor.org/)

[BiocManager](https://cran.r-project.org/web/packages/BiocManager/vignettes/BiocManager.html)

[pheatmap](https://cran.r-project.org/web/packages/pheatmap/index.html)

[ggplot2](https://cran.r-project.org/web/packages/ggplot2/index.html)

[ggplot2 tidyverse](https://ggplot2.tidyverse.org/)

[RNA-seq workflow](https://www.bioconductor.org/packages/devel/workflows/vignettes/rnaseqGene/inst/doc/rnaseqGene.html)

[Analyzing RNA-seq data with DESeq2](https://bioconductor.org/packages/devel/bioc/vignettes/DESeq2/inst/doc/DESeq2.html)

[DESeq2](https://bioconductor.org/packages/release/bioc/html/DESeq2.html)

[DESeq2 user manual](https://bioconductor.org/packages/devel/bioc/manuals/DESeq2/man/DESeq2.pdf)

[Genome Biology paper](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-014-0550-8)

[Beginner’s guide to using the DESeq2 package](https://bioc.ism.ac.jp/packages/2.14/bioc/vignettes/DESeq2/inst/doc/beginner.pdf)

[Differential analysis of count data by DESeq2](https://bioc.ism.ac.jp/packages/3.1/bioc/vignettes/DESeq2/inst/doc/DESeq2.pdf)

[EnhancedVolcano](https://bioconductor.org/packages/release/bioc/html/EnhancedVolcano.html)

[org.Hs.eg.db](https://bioconductor.org/packages/release/data/annotation/html/org.Hs.eg.db.html)

[clusterProfiler](https://bioconductor.org/packages/release/bioc/html/clusterProfiler.html)

[GeneCards](https://www.genecards.org/)

[HGNC](https://genename.org)
