# Organoid Leukemia Data Analysis

These scripts were developed by the author Philip Gebing as part of a PhD project at the University Clinic Düsseldorf (Department of Paediatric Oncology, Hematology, and Clinical Immunology) under supervision of Sanil Bhatia PhD and Ute Fischer PhD.

## Getting Started

This code was created to transform image data from confocal microscopy for further analysis. We input "positional data" i.e., coordinate data exported from "Imaris" software (Oxford Instruments, RRID:SCR_007370).

![TitleImage](https://github.com/BIOGOAT/organoid_leukemia_analysis/assets/103995515/83f51314-88f7-43cf-a304-bdd01cd9703d)

### Prerequisites and Installation
Ensure that you have have notebooks set up to run python code. The scripts included in this repository were written using Jupyter Notebook. Example data used for our manuscript submision to Blood Hematology, can be found under the `data` folder. One can also use their own data, so long as it is in the format seen in these example data.

Use the following command to install the dependencies using pip: 
```bash
pip install -r requirements.txt
```
This will run installation for all dependencies required in notebooks

Note that for smaller CPU only wheel on x86_64 Linux (v0.17+), one can opt for installing `open3d-cpu` as

```bash
pip install open3d-cpu
```

#### Open3D CLI
This package is used to create the poisson reconstruction [Kazhdan2006] of organoids, which is ultimately used to calculate the distances between the organoid surface and leukemia cells.
```bash
open3d example visualization/draw
```

## Contents
Files in the `notebooks` folder:
- `PDX_vs_Control.ipynb` - Jupyter notebook for calculating closest distance by cells determined from three independent experiments "KCL22", "K562", "PDX3", and "PDX1", each containing triplicate data with the paired image data for DOTS and VOL. Here, we illustrate the difference in distances calculated between triplicates of several leukemia entities (please refer to our manuscript).
- `Grid of Plots PDX_vs_Control.ipynb` - Jupyter notebook for visualizing 3D imaging data of organoids. Here we plot VOL and DOTS data for "KCL22", "K562", "PDX3, and "PDX1".

## Summary of the Analyses
All dataframes imported in these scripts undergo trimmings to remove headers and unneeded columns, before being used for plotting.
- The positional data (X,Y,Z coordinates) are imported from .xls file. These can be plotted as three scatter plots for each data sample. This will create three different plots showing XY, YZ, XZ 2D plots of the positional data. The Z-axis data are selected to produce the gradient color of the colorbar.
- The positional data are imported for both the organoids (VOL) and cells (DOTS) using the open3D package. Firstly, pointclouds (pcds) are created for both organoids and cells which will be used to run distance queries. The organoid data are then used to produce a poisson surface reconstruction. Finally, a dataframe is created using the 'dict' function which is then re-associated with the names of the original files. The seaborn package is then used to plot stripplots of the data.

## Data
To run with the original data, download it from (https://figshare.com/s/4835d0f62aabc61a8c64) and add the unzipped folder named `data` into `notebooks` folder.

## Authors

* **Philip Gebing**

See also [contributors](https://github.com/bazvalya) who participated in this project.


## Acknowledgments

* Hat tip to Valentina Bazyleva for her patience and guidance during my coding phase and help with this repository

## Package References

### Open3D

We have cited the Open3D package in our manuscript...

```bash
Zhou QY, Park J, Koltun V. Open3D: A Modern Library for 3D Data Processing. Published online January 29, 2018. Accessed February 21, 2023. http://arxiv.org/abs/1801.09847
```

## Versions

Please refer to requirements.txt for package versions used

## Citation

Please consider citing this work, if you find this repository useful for your work:

```bash
@article{10.1182/bloodadvances.2023011145,
    author = {Gebing, Philip and Loizou, Stefanos and Hänsch, Sebastian and Schliehe-Diecks, Julian and Spory, Lea and Stachura, Pawel and Jepsen, Vera H. and Vogt, Melina and Pandyra, Aleksandra A. and Wang, Herui and Zhuang, Zhengping and Zimmermann, Johannes and Schrappe, Martin and Cario, Gunnar and Alsadeq, Ameera and Schewe, Denis M. and Borkhardt, Arndt and Lenk, Lennart and Fischer, Ute and Bhatia, Sanil},
    title = {A brain organoid/ALL coculture model reveals the AP-1 pathway as critically associated with CNS involvement of BCP-ALL},
    journal = {Blood Advances},
    volume = {8},
    number = {19},
    pages = {4997-5011},
    year = {2024},
    month = {09},
    abstract = {Central nervous system (CNS) involvement remains a clinical hurdle in treating childhood B-cell precursor acute lymphoblastic leukemia (BCP-ALL). The disease mechanisms of CNS leukemia are primarily investigated using 2-dimensional cell culture and mouse models. Given the variations in cellular identity and architecture between the human and murine CNS, it becomes imperative to seek complementary models to study CNS leukemia. Here, we present a first-of-its-kind 3-dimensional coculture model combining human brain organoids and BCP-ALL cells. We noticed significantly higher engraftment of BCP-ALL cell lines and patient-derived xenograft (PDX) cells in cerebral organoids than non-ALL cells. To validate translatability between organoid coculture and in vivo murine models, we confirmed that targeting CNS leukemia–relevant pathways such as CD79a/Igα or C-X-C motif chemokine receptor 4–stromal cell-derived factor 1 reduced the invasion of BCP-ALL cells into organoids. RNA sequencing and functional validations of organoid-invading leukemia cells compared with the noninvaded fraction revealed significant upregulation of activator protein 1 (AP-1) transcription factor–complex members in organoid-invading cells. Moreover, we detected a significant enrichment of AP-1 pathway genes in PDX ALL cells recovered from the CNS compared with spleen blasts of mice that had received transplantation with TCF3::PBX1+ PDX cells, substantiating the role of AP-1 signaling in CNS disease. Accordingly, we found significantly higher levels of the AP-1 gene, jun proto-oncogene, in patients initially diagnosed as CNS-positive BCP-ALL compared with CNS-negative cases as well as CNS-relapse vs non–CNS-relapse cases in a cohort of 100 patients with BCP-ALL. Our results suggest CNS organoids as a novel model to investigate CNS involvement and identify the AP-1 pathway as a critical driver of CNS disease in BCP-ALL.},
    issn = {2473-9529},
    doi = {10.1182/bloodadvances.2023011145},
    url = {https://doi.org/10.1182/bloodadvances.2023011145},
    eprint = {https://ashpublications.org/bloodadvances/article-pdf/8/19/4997/2245594/blooda\_adv-2023-011145-main.pdf},
}

```

