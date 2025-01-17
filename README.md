[![DOI](https://zenodo.org/badge/684187842.svg)](https://zenodo.org/doi/10.5281/zenodo.13253143)

# meK-Means: Biophysically Motivated and Interpretable Inference of Cell Types from Multimodal Sequencing Data

Notebooks for reproducing all figures and analysis of simulated and single-cell datasets for the [meK-Means](https://www.biorxiv.org/content/10.1101/2023.09.17.558131v2.full.pdf) paper. All saved/processed data used for analysis can be found on [CaltechData](https://data.caltech.edu/search?q=meK-Means%20AND%20tara%20chari&f=resource_type%3Adataset&l=list&p=1&s=10&sort=bestmatch). Figure created with BioRender.com.
<div align="center"><img src="https://github.com/pachterlab/CGP_2023/blob/main/meK_pic.png" width="400"/></div>

## Getting Started
<div align="center">
   
<b>------ For a tutorial of how to use meK-Means -----</b>

See the [`example_meKMeans_notebook.ipynb`](https://github.com/tarachari3/CGP_2023/blob/main/example_meKMeans_notebook.ipynb)

</div>


<div align="center">
   
<b>------ For a tutorial in generating U and S counts -----</b>
   
See the [`get_data_example_notebook.ipynb`](https://github.com/tarachari3/CGP_2023/blob/main/get_data_example_notebook.ipynb).

</div>


For notebooks that run on Google Colab, you will see the Colab link included at the top of the notebook. Just click on the [![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com) symbol.

An introduction to using Google Colab can be found [here](https://colab.research.google.com). Briefly, run each code cell by selecting the cell and executing Command/Ctrl+Enter.

```
#To install meK-Means

pip install monod

import monod
from monod import mminference #Function implementing meK-Means algorithm
```

## Related Links

meK-Means utilizes the [Monod](https://monod-examples.readthedocs.io/en/latest/) package for single-cell, CME-based inference.

## Repo Directory Contents
1) [`example_meKMeans_notebook.ipynb`](https://github.com/tarachari3/CGP_2023/blob/main/example_meKMeans_notebook.ipynb): Tutorial notebook for using meK-Means to cluster single-cell RNA-seq data.

2) [`get_data_example_notebook.ipynb`](https://github.com/tarachari3/CGP_2023/blob/main/get_data_example_notebook.ipynb): Tutorial notebook of how to obtain U and S counts from single-cell RNA-seq FASTQs.
   
3) **analysis_notebooks**
  *All analysis notebooks from which the paper figures were generated. Each can be run standalone.*

   Main Figure Notebooks :
    * `Fig1_standard.ipynb`: Notebook for generating Fig. 1 standard clustering plots.
    * `Figs_2_3_plots.ipynb`: Notebook for generating Fig. 2 and 3 benchmark results plots.
    * `Fig4_explorData.ipynb`: Notebook for generating Fig. 4 exploratory analysis plots.

   Preprocessing Notebooks listed in order of operation, to generate U/S counts and simulations:
   1. `sim_benchmark_data_gen/alldataset_preprocess.ipynb`: Processes fastqs for all datasets used, into U/S counts.
   2. `sim_benchmark_data_gen/gen_benchmark_data.ipynb`: Processes `alldataset_preprocess` to select genes and save data for benchmarking. 
   3. `sim_benchmark_data_gen/gen_sims.ipynb`: Generates simulated, clustered data based on biophysical model of transcription.

   Other Analysis Notebooks:
    * `sim_benchmark_meK_Leiden_KMeans_GLUE`: Notebook for running meK-Means, Leiden, K-Means, GLUE on all benchmark and simulated data.
    * `sim_benchmark_WNN.ipynb`: Notebook for running Seurat WNN and MOFA+ on all benchmark and simulated data.
    * `sim_benchmark_scMDC_scVI.ipynb`: Notebook for running scVI and scMDC on all benchmark and simulated data (uses Colab GPU).
    * `Supp_dropout.ipynb`: Notebook for analysis of meK-Means with simulated dropout data.
    * `Supp_timing.ipynb`: Notebook for runtime benchmarking of meK-Means.


5) **analysis_output** 
    * Saved result files (clustering method results) from analysis notebooks.
  
6) **scripts** 
    * Python script to extract germ cell dataset metadata and scMixology data metadata.

7) **env**
    * Python Conda environment (py39.yml) for Linux.
    * R Conda environment (r_Seurat.yml) for Linux.



