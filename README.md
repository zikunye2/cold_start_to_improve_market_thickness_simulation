# cold_start_to_improve_market_thickness_simulation
Simulation code and data of the paper - cold start to improve market thickness
To begin with, we describe the simulation model built upon on the real
data of Platform O, the data and code of which is released to the
public. The goal of this simulation system is helping scholars get
deeper understanding on the online advertising systems, implementation
details of the experiments, and how two-side experiment can increase the
estimation bias.

*Advertising System and Cold Start Setting.* To simplify the advertising
mechanism of our simulator, we consider the CPC billing option and
first-price auction in our simulation, which means we use the clicks as
our cold start target instead of conversions. Equivalently, we have
disclosed and translated the ad’s CPA to the corresponding CPC by
multiplying the average conversion rate. All hyper-parameters including
cold start target *α*, cold start reward *β*, the number of impressions
within a whole cold start period *T*, the proportion of new and mature
ads, budget of ads are tuned to be close to the online system such that
the output metric of cold start success rate is close to the online
systems. Interested scholars can also change those hyper-parameters in
the code.

*Ground Truth CTR Model and pCTR Model.* The simulator is equipped with
a “ground truth” click-through model for each ad via fitting fixed
effect models (group by ads) on its historical impression and click
records. During the fitting, we use both historical and demographic
features of users, content information of ads. However, due the data
safety issue especially for the individual level information, we only
disclose the data of the feature independent term interpreted as
“feature-invariant ad CTR”. More specifically, we randomly sample 300
data points from the joint distribution of bidding price (linearly
scaled CPC) and the feature-invariant ad CTR. To add the user feature
related information into our CTR models, we incorporate demographic
features with the real marginal distribution including gender, location,
and age. Then we synthetically generate those feature related ground
true coefficient using random uniform distribution. In summary, for our
simulation system, we generate ground true linear CTR model for ad *j*
and impression *i* as
CTR<sub>*i**j*</sub> = Coefficient<sub>*j*</sub><sup>*T*</sup> × Feature<sub>*i*</sub> + Feature invariant CTR<sub>*j*</sub>.
For the CTR predicting model, we assume for mature ads, model parameters
are known, but for new ads we initialize Coefficient<sub>*j*</sub> as 0,
and initialize
Feature invariant CTR<sub>*j*</sub> ← 0.5 × Feature invariant CTR<sub>*j*</sub> + 0.5 × Average CTR,
which mimics advertising system’s practice using average CTR by ad
category as the initialization. Without loss of generality, one can tune
this hyper-parameter in the simulation system. For training this CTR
prediction model, we use the online stochastic gradient descent
algorithm to minimize the mean squared loss.

*Data Set.* In summary of data mentioned above, w
