# Network disruption: maximizing disagreement and polarization in social networks

Recent years have seen a marked increase in the spread of misinformation, a phenomenon which has been accelerated and amplified by social media such as Facebook and Twitter. Motivated by this reality, our paper [Network disruption:  maximizing disagreement and polarization in social networks](https://arxiv.org/abs/2003.08377) introduces a model of network disruption where an adversary can take over a limited number of user profiles in a social network with the aim of maximizing disagreement and/or polarization in the network. 

This repository contains the code, datasets, and figures used in our paper. It is organized as follows:

* graph_helper.ipynb: This code contains functions to evaluate polarization, disagreement, and the weighted sum objective. It also has functions for generating adjacency matrices and opinion vectors following the descriptions of the Erdős-Rényi model, preferential attachment model, and stochastic block model, as well as functions to visualize disrupted networks.

* heuristics.ipynb: The functions in this file implement the heuristics described in Section 5.1 of our paper.

* heuristics_helper.ipynb: This code contains functions to execute all of the heuristics on a graph for a specified range of the budget k, as well as plot_obj() to plot performance of heuristics across the three objectives.

* testing_\*.ipynb: Files of this format create a random graph using the model specified or using given data, and use compare_algorithms() from heuristics_helper.ipynb to create arrays tracking how disruption increases each of the objectives as a function of k. These arrays are then converted to .pkl files and stored in their respective folders.

* \*\_pkl/: These folders contain a .pkl file containing data on heuristics' performance for each objective.

* Reddit.mat: Reddit dataset used by Cameron Musco, Christopher Musco, and Charalampos Tsourakakis in their [paper](https://arxiv.org/abs/1712.09948).

* preprocess-twitter/: this folder contains the Twitter data set used by Cameron Musco, Christopher Musco, and Charalampos Tsourakakis in their [paper](https://arxiv.org/abs/1712.09948).

* graph_pkl.ipynb: This code reads in a .pkl file and plots heuristics' performance across three objectives.

* Figures/: this folder contains the figures used in our paper, which were produced by running the testing files.

A note on the Reddit and Twitter data sets: these data sets were originally collected by Abir De, Sourangshu Bhattacharya, Parantapa Bhattacharya, Niloy Ganguly, and Soumen Chakrabarti in their [paper from 2014](https://dl.acm.org/doi/10.1145/2661829.2662064). We obtained both data sets from Cameron Musco, Christopher Musco, and Charalampos Tsourakakis: the Twitter data set is on [their GitHub repository](https://github.com/tsourolampis/preprocess-twitter), while the Reddit data set was emailed to us by them. 

## Running an experiment

To run an experiment, one only needs to run the cells of a notebook that begins with "testing". Each notebook will have a cell specifying how the network is constructed, which can be modified for synthetic experiments. Running all cells will overwrite the .pkl files in the respective folder. These .pkl files can then be read by graph_pkl.ipynb, which can be run to visualize performance. Alternatively, one can call plot_obj within the testing file directly and bypass storing the data.

## Citation

Mayee Chen and Miklós Z. Rácz. Network disruption: maximizing disagreement and polarization in social networks. Preprint available at https://arxiv.org/abs/2003.08377, 2020.

> @unpublished{chenracz2020networkdisruption, 
> title={Network disruption: maximizing disagreement and polarization in social networks}, 
> author={Chen, Mayee and R{\'a}cz, Mikl{\'o}s Z.}, 
> year={2020}, 
> note={Preprint available at \url{https://arxiv.org/abs/2003.08377}}}

