# Organoid Leukemia Data Analysis

These scripts were developed as part of a PhD project at the University Clinic Düsseldorf (Department of Paediatric Oncology, Hematology, and Clinical Immunology) under supervision of Sanil Bhatia PhD and Ute Fische PhD.

## Getting Started

This code was created to transform image data from confocal microscopy for further analysis. We input "positional data" ie. coordinate data exported from "Imaris" software (Oxford Instruments, RRID:SCR_007370)

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
- `data` - Contains files with WRITE
Files in the `notebook` folder:
- `1857_Triplicate_Analysis.ipynb` - Jupyter notebook for calculating closest distance by cells determined from three sets of "paired image data" (each organoid image combines a DOTS and VOL file for both organoid and cancer cells respectively). Here, experimental triplicates for the cell type 'PDX' are analysed and plotted (please refer to our manuscript).

- `Leukemia_vs_Healthy.ipynb` - Jupyter notebook for calculating closest distance by cells determined from two independent experiments "Leukemia" and "Healthy", each containing triplicate data with the paired image data for DOTS and VOL. Here, we illustrate the difference in distances calculated between triplicates of leukemia cells, compared to those of healthy controls (please refer to our manuscript).

- `Other_Leukemia_Entities.ipynb` - Jupyter notebook for calculating closest distance by cells determined from three independent experiments "SUPB15", "697", and "Kasumi2", each containing triplicate data with the paired image data for DOTS and VOL. Here, we illustrate the difference in distances calculated between triplicates of several leukemia entities (please refer to our manuscript).
- `Scatter_Plots_Leukaemia_Healthy.ipynb` - 

## Summary of the Analyses
All dataframes imported in these scripts undergo trimmings to remove headers and unneeded columns, before being used for plotting.
### Grid of Scatter Plots (CHANGE)
The positional data (X,Y,Z coordinates) are imported from .xls file. These can be plotted as three scatter plots for each data sample. This will create three different plots showing XY, YZ, XZ 2D plots of the positional data. The Z-axis data are selected to produce the gradient color of the colorbar.
### Loops (CHANGE)
The positional data are imported for both the organoids (VOL) and cells (DOTS) using the open3D package. Firstly, pointclouds (pcds) are created for both organoids and cells which will be used to run distance queries. The organoid data are then used to produce a poisson surface reconstruction. Finally, a dataframe is created using the 'dict' function which is then re-associated with the names of the original files. The seaborn package is then used to plot strip and histplots of the data.


## Authors

* **Philip Gebing**

See also [contributors](https://github.com/bazvalya) who participated in this project.


## Acknowledgments

* Hat tip to Valentina Bazyleva for her patience and guidance during my coding phase and help with this repository
* Inspiration
* etc

# Package References

#---
#output:
 #md_document:
#variant: markdown_github
#bibliography: bibliography.bib
#---


## Open3D

[@Zhou2018]

```bash
@article{Zhou2018,
   author  = {Qian-Yi Zhou and Jaesik Park and Vladlen Koltun},
   title   = {{Open3D}: {A} Modern Library for {3D} Data Processing},
   journal = {arXiv:1801.09847},
   year    = {2018},
}
```

# Seaborn

[@Waskom2021]
```bash
@article{Waskom2021,
    doi = {10.21105/joss.03021},
    url = {https://doi.org/10.21105/joss.03021},
    year = {2021},
    publisher = {The Open Journal},
    volume = {6},
    number = {60},
    pages = {3021},
    author = {Michael L. Waskom},
    title = {seaborn: statistical data visualization},
    journal = {Journal of Open Source Software}
}
 ```
# Matplotlib 
[@Hunter:2007]
```bash
@Article{Hunter:2007,
  Author    = {Hunter, J. D.},
  Title     = {Matplotlib: A 2D graphics environment},
  Journal   = {Computing in Science \& Engineering},
  Volume    = {9},
  Number    = {3},
  Pages     = {90--95},
  abstract  = {Matplotlib is a 2D graphics package used for Python for
  application development, interactive scripting, and publication-quality
  image generation across user interfaces and operating systems.},
  publisher = {IEEE COMPUTER SOC},
  doi       = {10.1109/MCSE.2007.55},
  year      = 2007
}
```
 
 
## Citation

Please consider citing this work, if you find this repository useful for your work:

```bash
@article{PHILIP,
  title={TITLE PAPER},
  author={AUTHORS},
  journal={THE JOURNAL},
  volume={VOL},
  number={NUMBER},
  year={2023},
  publisher={PUBLISHER}
}
```

