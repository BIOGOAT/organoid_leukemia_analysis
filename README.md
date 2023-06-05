# Organoid Leukemia Data Analysis

One Paragraph of project description goes here

## Getting Started

This code was created to transform image data from confocal microscopy for further analysis. We input "positional data" ie. coordinate data exported from "Imaris" software (Oxford Instruments, RRID:SCR_007370)

### Prerequisites

Ensure that you have have notebooks set up to run python code. The scripts included in this repository were written using Jupyter Notebook. Example data used for our manuscript submision to Blood Hematology, can be found under the "data" folde. One can also use their own data, so long as it is in the format seen in these example data.

### Installing

#### Open3D
pip install open3d       # or
pip install open3d-cpu   # Smaller CPU only wheel on x86_64 Linux (v0.17+)

#### Verify installation
python -c "import open3d as o3d; print(o3d.__version__)"

#### Python API
python -c "import open3d as o3d; \
           mesh = o3d.geometry.TriangleMesh.create_sphere(); \
           mesh.compute_vertex_normals(); \
           o3d.visualization.draw(mesh, raw_mode=True)"

#### Open3D CLI
open3d example visualization/draw

#### Seaborn
pip install seaborn


## Running the Analyses

### Grid of Scatter Plots
### Loops



## Built With

* [open3d]

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

%what can I put here Valya?

## Authors

* **Philip Gebing**

See also the list of [contributors](https://github.com/BIOGOAT/organoid_leukemia_analysis/settings/access) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to Valentina Bazyleva for her patience and guidance during my coding phase
* Inspiration
* etc

