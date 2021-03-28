# Interactive maps of mutations to the SARS-CoV-2 RBD that reduce antibody binding or neutralization
Visualizations of the SARS-CoV-2 RBD "escape maps" that the Bloom lab has generated by using deep mutational scanning to map how all RBD mutations that affect antibody binding or neutralization.

These visualizations are rendered at [https://jbloomlab.github.io/SARS2_RBD_Ab_escape_maps](https://jbloomlab.github.io/SARS2_RBD_Ab_escape_maps).

The visualizations are built primarily by using [Altair](https://altair-viz.github.io/) for the interactive plotting, and then are all rendered on a webpage via [GitHub Pages](https://pages.github.com/).

The input data on how mutations affect antibody binding or neutralization are in [./data/](data), and is collated from Bloom lab deep mutational scanning experiments.
See [./data/README.md](data/README.md) for details on how to add new data.

To process the data to build the interactive visualizations, first build the `conda` environment in [environment.yml](environment.yml).
Then activate that `conda` environment with:

    conda activate SARS2_RBD_Ab_escape_maps

Next, process the raw data by running [process_data.py](process_data.py):

    python process_data.py

This command will process the input data in [./data/](data) to create the processed data in [./processed_data/](processed_data).
Specifically, the processed data includes the following two files:

 - [processed_data/escape_data.csv](processed_data/escape_data.csv) contains the raw escape data for all antibodies / sera.
 - [processed_data/studies.csv](processed_data/studies.csv) contains information on the studies.

The [process_data.py](process_data.py) script also adds information about citations to the bottom of [docs/index.md](docs/index.md) for rendering on the webpage.

Finally, open the Jupyter notebook [plot_data.ipynb](plot_data.ipynb) using `jupyterlab` and run it.
This creates the interactive [Altair](https://altair-viz.github.io/) plot and puts it in [docs/_includes/chart.html](docs/_includes/chart.html) where it can be rendered via GitHub pages.

When updates are pushed to the `main` branch of the repo on GitHub, they will be rendered at [https://jbloomlab.github.io/SARS2_RBD_Ab_escape_maps](https://jbloomlab.github.io/SARS2_RBD_Ab_escape_maps).
See [docs/README.md](docs/README.md) for more information on how the webpage is served via [GitHub Pages](https://pages.github.com/)
