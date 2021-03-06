# check-if-power-law

This is an example showing how we can validate the hypothesis that a distribution follows the power-law. For more details from the theoretical aspects, please refer to the paper "Power-law distributions in empirical data." by Clauset et al. or our [slides](https://github.com/xiaoylu/check-if-power-law/blob/master/Plotting_Power_laws_and_the_Degree_Exponent.pdf) for a quick glance.

## Organization
1. The step-by-step python code is in `powerlaw.ipynb`. 
2. The MLE estimator and goodness of fit are explained in the slides `Plotting_Power_laws_and_the_Degree_Exponent.pdf`.
3. The output figures are in `powerlaw_report.pdf`. We also consider fitting the data by the log-logistic distribution.
4. The parallelized synthetic data generation code can be found at `powerlaw_synthetic_parallel.py`. 
5. The dataset for this example is located at `news_events_powerlaw.csv`. It is the number of news event reported by the online news site in the last years. Data source: [GDelt](https://en.wikipedia.org/wiki/Global_Database_of_Events,_Language,_and_Tone).

## Figures 
Distribution of the real data in `news_events_powerlaw.csv` (as an example):

![alt text](https://github.com/xiaoylu/check-if-power-law/blob/master/figures/scatter.png "Distribtuion of the real data.")

The slope in double logarithm scale is the exponent of the power-law. KS distance measure the "distance" of the real data and obtained model. The minimum degree where the power-law starts is 2 here.

![alt text](https://github.com/xiaoylu/check-if-power-law/blob/master/figures/fit.png "Fit the data")

Using the obtained model, we generate synthetic sequences, which are used to evaluate the goodness of fit.

![alt text](https://github.com/xiaoylu/check-if-power-law/blob/master/figures/synthetic.png "synthetic sequences")

The p-value is exactly the portion of synthetic sequences whose KS distance is larger than the real data's. When p-value is large enough, >10% in most cases, we can say the Power-law is a plausible fit to the real data.

![alt text](https://github.com/xiaoylu/check-if-power-law/blob/master/figures/pvalue.png "pvalue")
