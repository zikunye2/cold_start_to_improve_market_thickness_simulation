In this repository, we open-source the code accompanying the empirical and simulation analyses of [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786).

# Empirical Analysis

## Table of contents of empirical analysis
* [General Info](#general-info-emp)
* [Files](#files-emp)
* [Instruction to produce figures, tables, results](#instr)
* [Data Dictionary](#dic-data)


<a id='general-info-emp'></a>
## General Info 
This empirical part contains the code (as Jupyter Notebooks) and data inputs to produce all figures, tables, and results in [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). To protect the sensitive data from our industry collaborator, the files provided in the Empirical Analysis section contain synthetic data only. The exactly replicate our empirical results, one needs to collaborate with an online advertising platform, deploy our proposed oSBL algorithm, run two-sided experiments as described in the paper, and access the proprietary data from the platform.


<a id='files-emp'></a>
## Files
* [empirical_analysis.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/empirical_analysis.ipynb): This is the code for the empirical analysis in [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). 

* [retention_data.csv'](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/retention_data.csv) This dataset contains the observational data before the experiment. Each row records the basic information ('imp', 'click_cnt', 'cvr_cnt', 'target_cost', 'cost_total', 'target_bid'), aggregated at day level ('p_date') of a specific ad ('unit_id').

* [randomization_check_data_block.csv](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/randomization_check_data_block.csv) This dataset is used for randomization check and constains ad performance data before the experiments. Each row records the basic information ('target_cost','cost_total','cvt_cnt','auto_cpa_bid','target_bid','imp','click'), aggregated at day level ('p_date') of a specific ad ('unit_id') with the field ('unit_tag') indicating whether the ad is in the treatment group or not.

* [exp_short_term_results.csv](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/exp_short_term_results.csv) This dataset contains the ad performance data during the experiment. Each row records the basic performance information aggregated at hour level ('p_date','p_hourmin') of a specific ad ('unit_id') with the assigned treatment conditions ('exp_tag','unit_tag').

* [exp_cost_results.csv](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/exp_cost_results.csv) This dataset contains the revenue performance aggregated at an hourly level during the experiment.

<a id='instr'></a>
## Instruction to Produce the Empirical Analysis

* [**Figure 1: Retention Rate**] can be produced by the Code Block-[Figure 1 with observational data] in [empirical_analysis.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/empirical_analysis.ipynb).
* [**Table 2: The Short-Term Effects of oSBL**] can be produced by the Code Block-[Section 6.1 Short-Term Performance of Our oSBL Algorithm] in [empirical analysis.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/empirical_analysis.ipynb).
* [**Table 3: The Long-Term Effects of oSBL**] and [**Figure 6: Effect of oSBL on Market Thickness**] can be produced by the Code Block-[Section 6.2 Long-term effects of oSBL] in [empirical analysis.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/empirical_analysis.ipynb).
* [**Figure 7: Global Treatment Effect of oSBL on Advertising Revenue**] can be produced by the Code Block-[Section 6.3 Global Treatment Effect of Our oSBL Algorithm on Advertising Revenue] in [empirical analysis.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/empirical_analysis.ipynb).
* [**Table 6: Randomization Check of the Experiment**] can be produced by the Code Block-[Section 5 Randomization check of field experiments] in [empirical analysis.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/empirical_analysis.ipynb).
* [**Figures 9, 10, 11**] can be produced by the Code Block-[Section 6.3 Global Treatment Effect of Our oSBL Algorithm on Advertising Revenue] in [empirical analysis.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/empirical_analysis.ipynb).

<a id='dic-data'></a>	
## Data Dictionary

| Column Name   | Meaning                            |
|---------------|------------------------------------|
| imp_id        | impression ID                      |
| unit_id       | ad ID                              |
| unit_tag      | treatment condition of ad          |
| exp_tag       | treatment condition of impression  |
| p_date        | date                               |
| p_hourmin     | hour                               |
| pxtr          | predicted ctr*cvr                  |
| retention_cnt | # of retention days                |
| cvt_cnt       | # of conversions during cold start |
| click         | # of clicks                        |
| imp           | # of impressions                   |
| auto_cpa_bid  | real-time bid                      |
| target_bid    | bid set by the advertiser          |
| cost_total    | real cost of ads                   |
| target_cost   | expected cost of ads               |



# Simulation System for Cold Start and Experimentation in Online Advertising

We provide the Python code of the simulation system built in [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). See Appendix D.1 of the paper for details of the simulation system. Please contact the authors of [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) if you have any questions or suggestions.


## Table of contents of simulation
* [General Info](#general-info)
* [Files](#files)
* [Simulation Details](#simulation-details)


<a id='general-info'></a>
## General Info 
This simulation part contains the code (as Jupyter Notebooks) and data inputs of the simulation system of the paper [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). The goal of releasing the code and data is to help interested scholars get deeper understanding on the operational details of the online advertising system, and the implementation of the single- and two-sided experiments studied in [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786).

<a id='files'></a>
## Files
* [cold_start_simulation.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb): The main simulation code. 
* [ctr_bid_data.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/ctr_bid_data.npy): The sampled data of click-through rates (CTR) and bid prices (to protect data security, these quantities are re-scaled by a random multiplier), 300 observations in total.
* [simulation_output](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output): The simulation results.

<a id='simulation-details'></a>	
## Simulation Details

To run the code of this project, please install [Python 3](https://www.python.org/downloads/) and [Jupyter Notebook](https://jupyter.org/install.html). Please refer to Appendix D.1 of [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for more information about the simulation system. [The code](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb) contains the following four modules:

* **Module I**: Two parallel simulations, one implementing the baseline ad delivery algorithm (i.e., the PID-controller driven bidding strategy) and the other implementing the Shadow Bidding with Learing and Dual Mirror Descent (SBL-DMD) Algorithm. See Section 4.1 and Appendix H.2 in [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for detailed introductions of the SBL-DMD and PID algorithms, respectively.
* **Module II**: The Ad-side and UV-side experiment designs. See Section 5.1 and Appendix D.1 of [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for details.
* **Module III**: The two-sided experiment design. See Section 5.1 and Appendix D.1 of [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for details.
* **Module IV**: Resampling the outcomes for hypothesis testing.

To evalute the performance of the estimators constructed from single- or two-sided experiments on an online advertising platform, we consider the following two metrics of interest in the simulation system (see Appendix D.1 of [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for details):

* **Cold start success rate**, defined as the proportion of new ads successfully cold started by the algorithm deployed;
* **Revenue**, total advertising revenue from new and mature ads on the platform.

Through the simulation system, we replicate different field experiment designs to evalute the effectiveness of the SBL-DMD algorithm proposed by [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786). The [simulation results](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output) show that:

* The **UV-side experiment design** significantly underestimates the cold start success rate, and significantly overestimates the revenue loss.
* The **ad-side experiment design** significantly overestimates the cold start success rate.
* The **two-side experiment** neither overestimates nor underestimates both performance metrics of interest.

Interested readers are also free to change the hyper-parameters in [the code](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb) of the simulation system, such as (see [Ye et al. (2022)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3702786) for the definition and interpretation of each parameter):

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
Ye, Zikun, Dennis Zhang, Heng Zhang, Renyu Zhang, Xin Chen, and Zhiwei Xu. 2022. Cold Start to Improve Market Thickness on Online Advertising Platforms: Data-Driven Algorithms and Field Experiments. *Management Science*, forthcoming. Available at: https://ssrn.com/abstract=3702786 and https://pubsonline.informs.org/doi/full/10.1287/mnsc.2022.4550.



