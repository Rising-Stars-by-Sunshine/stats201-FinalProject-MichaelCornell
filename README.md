# Michael Cornell's Project Portfolio

## Problem Set 2 - Notebook:

[Jupyter Notebook](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell/blob/main/code/autogluonTrafficModelPredictor.ipynb)

## Project information
- **Author**: Michael Cornell, Computation and Design - Computer Science Track, 2026, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: Submissions to Problem Set 2 for STATS201 Introduction to Machine Learning for Social Science, 2023 Spring Term (Seven Week - First) instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgments**: 
Many thanks to Professor Luyao Zhang for her careful instruction and to the authors of the Autogluon support documents.

- **Project Summary**: 
  - Background and Motivation: Traffic modeling has always been difficult to perform. With the advent of new machine learning models, many new opportunities arise to help engineers develop better ways to model traffic. 
  - Research Question: What's the best machine learning application to predict traffic modeling, and how can traffic be predicted over time? We will use Autogluon to help us answer this question.
  - Application Scenario: The research here focuses on trips taken by car at a National level in the United States from 2019-2021. The data comes from a United States government collection of driving behavior.
  - Methodology: The package Autogluon was used to predict future driving behavior beyond the scope of the data, and two separate types of analysis were performed. One allowed for covariate variables, such as whether or not a given day was a holiday or a weekend. The other analysis did not allow for this control.
  - Expected Results: We expect to see that traffic follows a weekly pattern, with increased traffic on holidays. We also expect that the machine learning algorithm will pick up on the trend of travel increasing back to normal levels during the recovery from the COVID-19 pandemic.
  - Intellectual Merit: This research will show that more advanced machine learning models are more helpful and accurate in predicting future traffic models. The results suggest that other fields relating to data forecasting may greatly benefit from the addition of a machine-learning model to help predict trends that legacy models may not pick up on.

## Table of Contents
- [Data](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell#data)
- [Code](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell#code)
- [Spotlight](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell#spotlight)
- [References](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell#references)



## Data
<div class="table-wrapper" markdown="block">

|                    |                                                    **Data Links**                                                              |                       **Data Description**                                      |
|--------------------|:------------------------------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------:|
| **Raw Data**       | [Trips by Distance](https://catalog.data.gov/dataset/trips-by-distance)                                                      | The Bureau of Transportation Statistics (BTS) collected data |
| **Queried Data**   | [Queried Data](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell/blob/main/data/Queried_Data)   | Data has been cleaned for feeding into the Autogluon algorithm.            |
| **Processed Data** | [Processed Data](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell/tree/main/data/Processed_Data)        | Future predictions made by Autogluon's top model. |

</div>

## Code
First, set up and install [Autogluon](https://github.com/autogluon/autogluon#example), and follow the instructions for **TimeSeriesPredictor**.
- **TimeSeriesPredictor** is available [here](https://github.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell/blob/main/code/autogluonTrafficModelPredictor.ipynb)

## Spotlight

|    | model                |   score_test |   score_val |   pred_time_test |   pred_time_val |   fit_time_marginal |   fit_order |
|---:|:---------------------|-------------:|------------:|-----------------:|----------------:|--------------------:|------------:|
|  0 | WeightedEnsemble     |   -0.0262796 |  -0.0262072 |        0.149497  |       0.151515  |         6.32498     |          20 |
|  1 | SimpleFeedForward/T2 |   -0.0301972 |  -0.0301972 |        0.0181561 |       0.0157161 |        37.4345      |          18 |
|  2 | ETS/T4               |   -0.0327488 |  -0.0327488 |        0.0102077 |       0.0749049 |         0.000177383 |           6 |
|  3 | SimpleFeedForward/T1 |   -0.0332227 |  -0.0332227 |        0.0165756 |       0.0163398 |        33.4099      |          17 |
|  4 | DeepAR/T1            |   -0.0349798 |  -0.0343736 |        0.122385  |       0.120849  |       363.592       |          15 |
|  5 | SimpleFeedForward/T3 |   -0.0367208 |  -0.0367208 |        0.0161967 |       0.0159767 |        34.2694      |          19 |
|  6 | ETS/T1               |   -0.0411622 |  -0.0411622 |        0.0105195 |       0.0864201 |         0.000215292 |           3 |
|  7 | DeepAR/T2            |   -0.041714  |  -0.0417324 |        0.135521  |       0.135799  |       430.265       |          16 |
|  8 | SeasonalNaive        |   -0.0427642 |  -0.0427642 |        0.0106621 |       2.82532   |         0.00245452  |           2 |
|  9 | Theta/T1             |   -0.0464423 |  -0.0464423 |        0.0102456 |       0.0998085 |         0.000169516 |           7 |
| 10 | ARIMA/T6             |   -0.0511988 |  -0.0511988 |        0.0102079 |       0.290755  |         0.00019145  |          14 |
| 11 | Theta/T2             |   -0.0537291 |  -0.0537291 |        0.010195  |       0.106301  |         0.000175238 |           8 |
| 12 | ETS/T3               |   -0.054     |  -0.054     |        0.0102711 |       0.0333762 |         0.00022006  |           5 |
| 13 | ARIMA/T5             |   -0.0548981 |  -0.0548981 |        0.0102057 |       0.146896  |         0.000212193 |          13 |
| 14 | ARIMA/T4             |   -0.0564772 |  -0.0564772 |        0.0103984 |       0.436915  |         0.000208855 |          12 |
| 15 | ARIMA/T3             |   -0.0570744 |  -0.0570744 |        0.0101988 |       0.279418  |         0.000211477 |          11 |
| 16 | Naive                |   -0.0613421 |  -0.0613421 |        0.0130537 |       3.09628   |         0.00106454  |           1 |
| 17 | ARIMA/T1             |   -0.0625109 |  -0.0625109 |        0.010247  |       0.101825  |         0.000183105 |           9 |
| 18 | ETS/T2               |   -0.0634961 |  -0.0634961 |        0.0102322 |       0.0420156 |         0.00022459  |           4 |
| 19 | ARIMA/T2             |   -0.0660468 |  -0.0660468 |        0.0101981 |       1.01988   |         0.000184059 |          10 |

***Figure No.1**. Performance of all Evaluated Models. Note that FeedForward and DeepAR perform quite well.* 

<img src="https://raw.githubusercontent.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell/main/spotlight/figures/figure2.png" alt="Figure2"/><br/>
***Figure No.2**. Model predictions when allowed for covariate variables. Holidays and weekends were among the static covariate variables.*   


<img src="https://raw.githubusercontent.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell/main/spotlight/figures/figure3.png" alt="Figure2"/><br/>
***Figure No.3**. Same as Figure 2, but includes all collected data.*


<img src="https://raw.githubusercontent.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell/main/spotlight/figures/figure4.png" alt="Figure2"/><br/>
***Figure No.4**. Predictions from SimpleFeedForward/T2, a machine learning model. This model had the second-highest score test.*


<img src="https://raw.githubusercontent.com/Rising-Stars-by-Sunshine/stats201-PS2-MichaelCornell/main/spotlight/figures/figure5.png" alt="Figure2"/><br/>
***Figure No.5**. Predictions from ARIMA/T1. This model had the third-lowest score test.*


## References

### Data Source
- Trips By Distance: https://catalog.data.gov/dataset/trips-by-distance
### Code Source
- Autogluon: https://github.com/autogluon/autogluon
  - Forecasting a time series: https://auto.gluon.ai/stable/tutorials/timeseries/forecasting-quickstart.html
### Literature

El Khateeb, S., & Shawket, I. M. (2022). A new perception; generating well-being urban public spaces after the era of pandemics. Developments in the Built Environment, 9, 100065. doi:10.1016/j.dibe.2021.100065

Erickson, N., Mueller, J., Shirkov, A., Zhang, H., Larroy, P., Li, M., & Smola, A. (2020). AutoGluon-Tabular: Robust and Accurate AutoML for Structured Data. ArXiv Preprint ArXiv:2003. 06505.

García-García, J. C., García-Ródenas, R., López-Gómez, J. A., & Martín-Baos, J. Á. (2022). A comparative study of machine learning, deep neural networks and random utility maximization models for travel mode choice modelling. Transportation Research Procedia, 62, 374–382. doi:10.1016/j.trpro.2022.02.047

S. Alfosool, A. M., Chen, Y., & Fuller, D. (2022). ALF–Score—A novel approach to build a predictive network–based walkability scoring system. PLOS ONE, 17(6), e0270098. https://doi.org/10.1371/journal.pone.0270098

```
@article{agtabular,
  title={AutoGluon-Tabular: Robust and Accurate AutoML for Structured Data},
  author={Erickson, Nick and Mueller, Jonas and Shirkov, Alexander and Zhang, Hang and Larroy, Pedro and Li, Mu and Smola, Alexander},
  journal={arXiv preprint arXiv:2003.06505},
  year={2020}
}
```

