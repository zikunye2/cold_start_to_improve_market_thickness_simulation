# Simulation System for Cold Start in Advertising

We provide the Python code of the simulation system built in [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). See Appendix D.1 of the paper for details of the simulation system. Please contact the authors of [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) if you have any questions or suggestions.


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
* [ctr_bid_data.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/ctr_bid_data.npy): The sampled data of click-through rates (CTR) and bid prices (to protect data security, these quantities are re-scaled by a random multiplier), 300 observations in total.
* [simulation_output](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output): The simulation results.

<a id='simulation-details'></a>	
## Simulation Details

To run the code of this project, please install [Python 3](https://www.python.org/downloads/) and [Jupyter Notebook](https://jupyter.org/install.html). Please refer to Appendix D.1 of [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for more information about the simulation system. [The code](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb) contains the following four modules:

* **Module I**: Two parallel simulations, one implementing the baseline ad delivery algorithm (i.e., the PID-controller driven bidding strategy) and the other implementing the Shadow Bidding with Learing and Dual Mirror Descent (SBL-DMD) Algorithm. See Section 4.1 and Appendix H.2 in [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for detailed introductions of the SBL-DMD and PID algorithms, respectively.
* **Module II**: The Ad-side and UV-side experiment designs. See Section 5.1 and Appendix D.1 of [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for details.
* **Module III**: The two-sided experiment design. See Section 5.1 and Appendix D.1 of [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for details.
* **Module IV**: Resampling the outcomes for hypothesis testing.

To evalute the performance of the estimators constructed from single- or two-sided experiments on an online advertising platform, we consider the following two metrics of interest in the simulation system (see Appendix D.1 of [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for details):

* **Cold start success rate**, defined as the proportion of new ads successfully cold started by the algorithm deployed;
* **Revenue**, total advertising revenue from new and mature ads on the platform.

Through the simulation system, we replicate different field experiment designs to evalute the effectiveness of the SBL-DMD algorithm proposed by [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). The [simulation results](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output) show that:

* The **UV-side experiment design** significantly underestimates the cold start success rate, and significantly overestimates the revenue loss.
* The **ad-side experiment design** significantly overestimates the cold start success rate.
* The **two-side experiment** neither overestimates nor underestimates both performance metrics of interest.

Interested readers are also free to change the hyper-parameters in [the code](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb) of the simulation system, such as (see [Ye et al. (2021)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for the definition and interpretation of each parameter):

* The cold start success threshold.
* The cold start reward of each ad.
* The coefficients of the PID-controller.
* The initialized dual variables and learning rate of the SBL-DMD algorithm.
* The sampling rate of each experiment.
* The auction mechanism (first-price or second-price). 
* The billing option (pay-by-impression, pay-by-click, pay-by-action, etc.)
* The ground-truth CTR model.
* The machine learning oracle for predicting CTR.

## Reference
Ye, Zikun, Dennis Zhang, Heng Zhang, Renyu Zhang, Xin Chen, and Zhiwei Xu. 2021. Cold Start to Improve Market Thickness on Online Advertising Platforms: Data-Driven Algorithms and Field Experiments. Available at SSRN: https://ssrn.com/abstract=3702786 or http://dx.doi.org/10.2139/ssrn.3702786.

