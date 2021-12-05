# Cold Start to Improve Market Thickness Simulation


## Table of contents
* [General Info](#general-info)
* [Files](#files)
* [Simulation Details](#simulation-details)

## General Info
This project contains the simulation code (jupyter notebook) and data of the paper - cold start to improve market thickness.
The goal of this released code and data is helping scholars get
deeper understanding on the online advertising systems, implementation
details of our experiments, and how two-side experiment can decrease the
estimation bias.


## Files
* cold_start_simulation.ipynb: main simulation code 
* ctr_bid_data.npy: CTR and bid data
* simulation_output: outcome of the simulation
	
## Simulation Details
To run this project, please install Python 3. The jupyter notebook contains four parts:
* Part I: two parallel simulations using baseline ad delivery algorithm (PID) and ou proposed algorithm SBL-DMD
* Part II: Ad-side and UV-side field experiments
* Part III: Two-side field experiment
* Part IV: Replications for hypothesis testing

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


