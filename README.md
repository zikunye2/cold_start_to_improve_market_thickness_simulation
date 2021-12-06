# Simulation System for Cold Start in Advertising

We provide the Python code of the simulation system built in [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). See Appendix D.1 of the paper for details of the simulation system.


## Table of contents
* [General Info](#general-info)
* [Files](#files)
* [Simulation Details](#simulation-details)


<a id='general-info'></a>
## General Info 
This project contains the code (as Jupyter Notebooks) and data inputs of the simulation system of the paper [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). The goal of releasing the code and data is to help interested scholars get deeper understanding on the operational details of the online advertising system, and the implementation of the single- and two-sided experiments studied in [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786).

<a id='files'></a>
## Files
* [cold_start_simulation.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb): The main simulation code. 
* [ctr_bid_data.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/ctr_bid_data.npy): The sampled data of click-through rates (CTR) and bid prices, 300 observations in total.
* [simulation_output](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output): The simulation results.

<a id='simulation-details'></a>	
## Simulation Details

To run the code of this project, please install [Python 3](https://www.python.org/downloads/) and [Jupyter Notebook](https://jupyter.org/install.html). Please refer to Appendix D.1 of [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for more information about the simulation system. [The code](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb) contains the following four modules:

* **Module I**: Two parallel simulations, one implementing the baseline ad delivery algorithm (i.e., the PID-controller driven bidding strategy) and the other implementing the Shadow Bidding with Learing and Dual Mirror Descent (SBL-DMD) Algorithm. See Section 4.1 and Appendix H.2 in [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for detailed introductions of the SBL-DMD and PID algorithms, respectively.
* **Module II**: The UV-side and ad-side experiment designs. See Section 5.1 and Appendix D.1 of [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for details.
* **Module III**: The two-sided experiment design. See Section 5.1 and Appendix D.1 of [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for details.
* **Module IV**: Resampling the outcomes for hypothesis testing.

To evalute the performance of estimators, we report the following two metrics in experiments:

* Cold start success rate
* Revenue

We replicate different field experiment designs to evalute the effectiveness of our proposed SBL-DMD. The result shows that:
* Ad-side experiment significantly overestimates the cold start success rate, and cannot evalute the revenue loss
* UV-side experiment significantly underestimate the cold start success rate, and significantly overestimate the revenue loss
* Two-side experiment neither significantly overestimate nor underestimate both cold start success rate and revenue loss

One can also directly change hyperparameters in the code including:
* Cold start objective function parameters
* PID related coefficients
* SBL-DMD initialization, and learning rate
* Sampling rates of all experiments
* For other more fundamental settings including auction mechanisms, CTR predicting models, other cold start algorithms and experiment designs, and long-term behavior of advertisers, one needs to change codes correspondingly 

## Reference
Ye, Zikun and Zhang, Dennis and Zhang, Heng and Zhang, Renyu and Chen, Xin and Xu, Zhiwei. 2021. Cold Start to Improve Market Thickness on Online Advertising Platforms: Data-Driven Algorithms and Field Experiments. Available at SSRN: https://ssrn.com/abstract=3702786 or http://dx.doi.org/10.2139/ssrn.3702786.

