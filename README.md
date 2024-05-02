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
- The positional data are imported for both the organoids (VOL) and cells (DOTS) using the open3D package. Firstly, pointclouds (pcds) are created for both organoids and cells which will be used to run distance queries. The organoid data are then used to produce a poisson surface reconstruction. Finally, a dataframe is created using the 'dict' function which is then re-associated with the names of the original files. The seaborn package is then used to plot strip and histplots of the data.

## Data
To run with the original data, download it from https://figshare.com/articles/dataset/data_zip/23515965 and add the unzipped folder named `data` into `notebooks` folder.

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

