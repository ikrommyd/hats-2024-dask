# Dask for HEP tutorial
This is the companion repository to [PyHEP topical meeting - Dask](https://indico.cern.ch/event/1027094/).
A short introductory talk is available [here](https://indico.cern.ch/event/1027094/contributions/4312696/attachments/2239462/3796674/pyhep-dask.pdf) and a recording is available on [youtube](https://www.youtube.com/watch?v=BmmVmKHEcsc&list=PLKZ9c4ONm-VnFUD0XX2DmfP1JA8VIRhXP)

## Binder
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/nsmith-/dask-hep-tutorial/HEAD)

## Conda setup
We use the [coffea](https://coffeateam.github.io/coffea/) package to quickly get HEP dependencies like xrootd, uproot, etc.
Otherwise this is a standard scipy stack
```bash
conda create -n dask-hep-tutorial --yes -c conda-forge coffea dask distributed jupyterlab dask-labextension python-graphviz mimesis
conda activate dask-hep-tutorial
```

Now we can start the jupyter lab server:
```bash
jupyter lab
```

## Docker setup
We start with an image built for [coffea](https://coffeateam.github.io/coffea/) to get HEP dependencies like xrootd, uproot, etc.
Otherwise this is a standard scipy stack
```bash
docker run -it --rm -p 8888:8888 -p 8787:8787 -v ${PWD}:/srv coffeateam/coffea-dask bash
```

We will add a few extras to help showcase more of dask:
```bash
cd srv
conda install --yes -c conda-forge python-graphviz mimesis
```

Now we can start the jupyter lab server:
```bash
jupyter lab --allow-root --ip 0.0.0.0
```
