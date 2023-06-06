# Organoid Leukemia Data Analysis

These scripts were developed as part of a PhD project at the University Clinic Düsseldorf (Department of Paediatric Oncology, Hematology, and Clinical Immunology) under supervision of Sanil Bhatia PhD and Ute Fische PhD.

## Getting Started

This code was created to transform image data from confocal microscopy for further analysis. We input "positional data" ie. coordinate data exported from "Imaris" software (Oxford Instruments, RRID:SCR_007370)

### Prerequisites

Ensure that you have have notebooks set up to run python code. The scripts included in this repository were written using Jupyter Notebook. Example data used for our manuscript submision to Blood Hematology, can be found under the "data" folde. One can also use their own data, so long as it is in the format seen in these example data.

### Installation
Wse the following command to install the dependencies using pip: 
```bash
pip install -r requirements.txt
```
This will run installation for all dependencies required in notebooks

#### Open3D
```
pip install open3d
```
or
```
pip install open3d-cpu   # Smaller CPU only wheel on x86_64 Linux (v0.17+)
```
#### Verify installation
```
python -c "import open3d as o3d; print(o3d.__version__)"
```

#### Python API
```
python -c "import open3d as o3d; \
           mesh = o3d.geometry.TriangleMesh.create_sphere(); \
           mesh.compute_vertex_normals(); \
           o3d.visualization.draw(mesh, raw_mode=True)"
```

#### Open3D CLI
```
open3d example visualization/draw
```

#### Seaborn
```
pip install seaborn
```

## Running the Analyses
All dataframes imported in these scripts undergo trimmings to remove headers and unneeded columns, before being used for plotting.
### Grid of Scatter Plots
The positional data (X,Y,Z coordinates) are imported from .xls file. These can be plotted as three scatter plots for each data sample. This will create three different plots showing XY, YZ, XZ 2D plots of the positional data. The Z-axis data are selected to produce the gradient color of the colorbar.
### Loops
The positional data are imported for both the organoids (VOL) and cells (DOTS) using the open3D package. Firstly, pointclouds (pcds) are created for both organoids and cells which will be used to run distance queries. The organoid data are then used to produce a poisson surface reconstruction. Finally, a dataframe is created using the 'dict' function which is then re-associated with the names of the original files. The seaborn package is then used to plot strip and histplots of the data.


## Built With

* [open3d]
* [seaborn]
* [Matplotlib]

## Contributing

No contributions are required.

## Versioning

What can I put here Valya?

## Authors

* **Philip Gebing**

See also the list of [contributors](https://github.com/BIOGOAT/organoid_leukemia_analysis/settings/access) who participated in this project.

## License

Do we need this?

## Acknowledgments

* Hat tip to Valentina Bazyleva for her patience and guidance during my coding phase
* Inspiration
* etc

