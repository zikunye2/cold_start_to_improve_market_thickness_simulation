# Simulation Results
This folder contains simulation outputs of [cold_start_simulation.ipynb](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb). The outputs are exported as the numpy one-dimensional array data type, where each component represents one replication. More specifically, in each independent replication *i*, we resample all ads with new bids and CTRs and then run all experiments to output estimators in the *i*-th component of the corresponding array.


## Outputs
* [true_cs_value.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/true_cs_value.npy): unbiased value of the cold start success rate
* [estimator_cs_ad.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_cs_ad.npy): value of the cold start success rate estimators in Ad-side experiments
* [estimator_cs_uv.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_cs_uv.npy): value of the cold start success rate estimators in UV-side experiments
* [estimator_cs_two.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_cs_two.npy): value of the cold start success rate estimators in Two-side experiments
* [true_rev_value.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/true_rev_value.npy): unbiased value of the relative revenue change
* [estimator_rev_uv.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_rev_uv.npy): value of the relative revenue change estimators in UV-side experiments
* [estimator_rev_two.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_rev_two.npy): value of the relative revenue change estimators in Two-side experiments
