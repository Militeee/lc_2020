# lc_2020
Lab course 2020 material (Saur lab TUM) Bioinformatics section

## ScRNA-seq practical

The practical will consist in an end-to-end analysis of a cancer dataset. We will skip the alignment part as it is too computationally demandind and start directly with the counts data.
I ask you to install some specific package, just enter in a directory and run this section in your R console (either in RStudio or in the terminal)

```r
destfile = "./steele_data.rda"
dir_lab = "./lab_cpurse_SC"

if(!dir.exists(dir_lab)) dir.create(dir_lab)
setwd(dir_lab)
if(!file.exists(destfile)) download.file(url = "https://github.com/Militeee/lc_2020/raw/main/data/steele_data.rda", destfile = destfile)

curl::curl_download(url = 'http://pklab.med.harvard.edu/velocyto/mouseBM/SCG71.loom', destfile = './SCG71.loom')

if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

# if reticulate asks for miniconda type yes
install.packages(c("ggplo2", "dplyr", "RColorBrewer", "reticulate", "cowplot"))
BiocManager::install(c("fgsea", "Seurat", "scran", "scater"))


reticulate::py_install("leidenalg", pip = T)

```
Some packages are pretty big and need compilation so it may take a while. 
If you have any problem with the installation or have any question about the lesson and scRNA-seq just write me an email <militesalvatore@gmail.com>


The notebook for the lesson can be downloaded [here](https://github.com/Militeee/lc_2020/raw/main/lab_course_scrnaseq.Rmd) and the slides [here](https://github.com/Militeee/lc_2020/raw/main/08_12_20_labcourse_lez1.pdf)
