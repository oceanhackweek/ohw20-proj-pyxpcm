# ohw20-proj-pyxpcm
OceanHackWeek 2020 project on pyXpcm

## Installation
```git clone https://github.com/oceanhackweek/ohw20-proj-pyxpcm.git
conda env create -f ohw20-proj-pyxpcm.yml
conda activate ohw20-proj-pyxpcm
pip install pyxpcm
```

## Introduction
Use the package [pyXpcm](https://pyxpcm.readthedocs.io/) to identify ocean regions. 

pyXpcm is a Python package that performs  Profile Classification Model for ocean data, a statistical procedure to classify ocean vertical profiles into a finite set of “clusters”, based on a Gaussia Mixture Model. Depending on the dataset, such clusters can show space/time coherence that can be used in many different ways to study the ocean.

It consists in conducting un-supervised classification (clustering) with vertical profiles of one or more ocean variables.

Each levels of the vertical axis of each ocean variables are considered a feature. One ocean vertical profile with ocean variables is considered a sample.

## The problem
Building off of [Rosso et al., 2020](https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/2019JC015877) and previous work ( [Maze et al., 2017](https://www.sciencedirect.com/science/article/abs/pii/S0079661116300714?via%3Dihub) and [Jones et al., 2019](https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/2018JC014629) ), I'd like to construct a toolbox to apply the Profile Classification Model used in that paper and others to identify ocean mixing in a generalized context. Previous papers have focused on two regions, and are possibly hard coded in order to take in the data and run the unsupervised machine learning, I'd like to generalize the framework around the algorithms in order to look at ocean (possibly atmospheric) mixing anywhere in the world.


## Practical Steps
1. Reproduce the 'getting started/user guide' of pyXpcm.
    For this we use the example data provided in the package
2. Try out the classification by ourselves, from the start. For that, we need:
    a. Fetch Argo data for the North Atlantic, using [ArgoPy](https://github.com/euroargodev/argopy) (Choose a snapshot in time of the data)
    b. 'Clean' the data (remove un-necessary variables).
    c. Reduce the (vertical) dimensionality by performing a PCA (using scikit-learn?)
    d. Prepare the PCM model, by choosing the features (e.g. temperature and salinity) and the number of classes/clusters k.
    e. Use the pre-processed Argo data as an input for the model.
    f. Does the clustering changes when different time snapshots are used? (i.e, January Vs. July)
3. Try the classification with different data sources (maybe [glyder data](https://spraydata.ucsd.edu/projects/CUGN/), or satellite SST?)

## Participants
Carolina Camargo
Nora Loose
Daniela Munguia
Chandana Mudeppa
Shikha Singh
Joseph Gum
