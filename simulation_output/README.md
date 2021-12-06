# Simulation Results

This folder contains simulation outputs of our [simulation system](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb). The outputs are exported as the ``numpy`` one-dimensional array data type, where each component represents one replication. More specifically, in each independent simulation replication *i*, we resample all the ads with bid prices and CTRs following the ground-truth model, and then run all the experiments to store the estimators in the *i*-th component of the corresponding array.


## Outputs

Below we summarize the simulation results of the [simulation system](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/blob/main/cold_start_simulation.ipynb).

* [true_cs_value.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/true_cs_value.npy): The unbiased value of the cold start success rate, produced by parallel simulations.

* [estimator_cs_ad.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_cs_ad.npy): The value of the cold start success rate estimate produced by the ad-side experiment.

* [estimator_cs_uv.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_cs_uv.npy): The value of the cold start success rate estimate produced by the UV-side experiment.

* [estimator_cs_two.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_cs_two.npy): The value of the cold start success rate estimate produced by the two-sided experiment.

* [true_rev_value.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/true_rev_value.npy): The unbiased estimate of the relative effective size on revenue, produced by parallel simulations.

* [estimator_rev_uv.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_rev_uv.npy): The unbiased estimate of the relative effective size on revenue produced by the UV-side experiment.

* [estimator_rev_two.npy](https://github.com/zikunye2/cold_start_to_improve_market_thickness_simulation/tree/main/simulation_output/estimator_rev_two.npy): The unbiased estimate of the relative effective size on revenue produced by the two-sided experiment.
