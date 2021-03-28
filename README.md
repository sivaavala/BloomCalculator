# Interactive maps of mutations to the SARS-CoV-2 RBD that reduce antibody binding or neutralization
This repo creates a visualization of the SARS-CoV-2 RBD "escape maps" that the Bloom lab has generated by using deep mutational scanning to map how all RBD mutations that affect antibody binding or neutralization.
It uses [Altair](https://altair-viz.github.io/) for the interactive plotting.

The input data on how mutations affect antibody binding or neutralization are in [./data/](data), and is collated from Bloom lab deep mutational scanning experiments.
This is the only place you should add data.
See [./data/README.md](data/README.md) for details on how to add new data.

To process the data to build the interactive visualizations, first build the `conda` environment in [environment.yml](environment.yml).
Then activate that `conda` environment with:

    conda activate SARS2_RBD_Ab_escape_maps

Next, process the raw data by running [process_data.py](process_data.py):

    python process_data.py

This command will process the input data in [./data/](data) to create the processed data in [./processed_data/](processed_data).

Finally, open the Jupyter notebook [plot_data.ipynb](plot_data.ipynb) using `jupyterlab` and run it.
This will create the interactive chart in [./plots/](plots).
