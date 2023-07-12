# Employee Retention Project: ML
Predict whether or not an employee will leave the company.

## Business Scenario and Problem
The HR department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company. They collected data from employees, but now they don’t know what to do with it. They refer to you as a data analytics professional and ask you to provide data-driven suggestions based on your understanding of the data. They have the following question: what’s likely to make the employee leave the company?

The goal in this project is to analyze the data collected by the HR department and to build a model that predicts whether or not an employee will leave the company.

If we can predict employees likely to quit, it might be possible to identify factors that contribute to their leaving. Because it is time-consuming and expensive to find, interview, and hire new employees, increasing employee retention will be beneficial to the company.

## EDA
![fig1](https://github.com/osamabg1999/Employee-Retention---ML/assets/110773783/e01696fd-3ef1-4869-87f5-929b53d51181)
It might be natural that people who work on more projects would also work longer hours. This appears to be the case here, with the mean hours of each group (stayed and left) increasing with number of projects worked. However, a few things stand out from this plot.

There are two groups of employees who left the company: (A) those who worked considerably less than their peers with the same number of projects, and (B) those who worked much more. Of those in group A, it's possible that they were fired. It's also possible that this group includes employees who had already given their notice and were assigned fewer hours because they were already on their way out the door. For those in group B, it's reasonable to infer that they probably quit. The folks in group B likely contributed a lot to the projects they worked in; they might have been the largest contributors to their projects.

Everyone with seven projects left the company, and the interquartile ranges of this group and those who left with six projects was ~255–295 hours/week—much more than any other group.

The optimal number of projects for employees to work on seems to be 3–4. The ratio of left/stayed is very small for these cohorts.

If you assume a work week of 40 hours and two weeks of vacation per year, then the average number of working hours per month of employees working Monday–Friday = 50 weeks * 40 hours per week / 12 months = 166.67 hours per month. This means that, aside from the employees who worked on two projects, every group—even those who didn't leave the company—worked considerably more hours than this. It seems that employees here are overworked.

![fig2](https://github.com/osamabg1999/Employee-Retention---ML/assets/110773783/b15b3e31-3ea7-4f06-9a97-299cc442c136)

The scatterplot above shows that there was a sizeable group of employees who worked ~240–315 hours per month. 315 hours per month is over 75 hours per week for a whole year. It's likely this is related to their satisfaction levels being close to zero.

The plot also shows another group of people who left, those who had more normal working hours. Even so, their satisfaction was only around 0.4. It's difficult to speculate about why they might have left. It's possible they felt pressured to work more, considering so many of their peers worked more. And that pressure could have lowered their satisfaction levels.

Finally, there is a group who worked ~210–280 hours per month, and they had satisfaction levels ranging ~0.7–0.9.

![fig3](https://github.com/osamabg1999/Employee-Retention---ML/assets/110773783/467f1a95-9b5e-4db4-857a-514caeb5322b)

Employees who left fall into two general categories: dissatisfied employees with shorter tenures and very satisfied employees with medium-length tenures.

Four-year employees who left seem to have an unusually low satisfaction level. It's worth investigating changes to company policy that might have affected people specifically at the four-year mark, if possible.

The longest-tenured employees didn't leave. Their satisfaction levels aligned with those of newer employees who stayed.

The histogram shows that there are relatively few longer-tenured employees. It's possible that they're the higher-ranking, higher-paid employees.

![fig4](https://github.com/osamabg1999/Employee-Retention---ML/assets/110773783/83098eae-d567-4fbc-aeb8-db94cecd3940)

The plots above show that long-tenured employees were not disproportionately comprised of higher-paid employees.

![fig5](https://github.com/osamabg1999/Employee-Retention---ML/assets/110773783/a34f1dcc-dc97-4880-97e2-1b66fc8ec304)

The following observations can be made from the scatterplot above:

- The scatterplot indicates two groups of employees who left: overworked employees who performed very well and employees who worked slightly under the nominal monthly average of 166.67 hours with lower evaluation scores.

- There seems to be a correlation between hours worked and evaluation score.

- There isn't a high percentage of employees in the upper left quadrant of this plot; but working long hours doesn't guarantee a good evaluation score.

- Most of the employees in this company work well over 167 hours per month.

## Insights
It appears that employees are leaving the company as a result of poor management. Leaving is tied to longer working hours, many projects, and generally lower satisfaction levels. It can be ungratifying to work long hours and not receive promotions or good evaluation scores. There's a sizeable group of employees at this company who are probably burned out. It also appears that if an employee has spent more than six years at the company, they tend not to leave.

## Modelling

### Goal
The goal is to predict whether an employee leaves the company, which is a categorical outcome variable. So this task involves classification. More specifically, this involves binary classification, since the outcome variable left can be either 1 (indicating employee left) or 0 (indicating employee didn't leave).

### Comparing models
![compare](https://github.com/osamabg1999/Employee-Retention---ML/assets/110773783/310d6bcd-1928-4535-9c0c-d6b14be950fc)

### Best model results
![model](https://github.com/osamabg1999/Employee-Retention---ML/assets/110773783/e367e410-a4d4-4c9e-b4be-3369931a4612)

The classification report above shows that the LGBM Classifier model achieved a precision of 98.8%, recall of 91.8%, f1-score of 95.2%, and accuracy of 98.4%. Since it's most important to predict employees who leave, our recall score of 91.8% is pretty good.

![feature-imp](https://github.com/osamabg1999/Employee-Retention---ML/assets/110773783/510fb527-dfe6-4a0d-b54d-0e3ada1a0056)

## Conclusion and Recommendations¶
The models and the feature importances extracted from the models confirm that employees at the company are overworked.

To retain employees, the following recommendations could be presented to the stakeholders:

- Limit the amount of projects on which employees can work.
- Consider promoting employees who have been with the company for at least four years, or look into why four-year tenured employees are so unhappy.
- Employees should either be rewarded for working longer hours or not be required to do so.
- If employees are unaware of the company's overtime pay regulations, inform them. If the expectations for workload and vacation time are not plain, make them so.
- Hold company-wide and within-team talks to better understand and address the company's work culture, both globally and in specific settings.
- Employees who work 200+ hours per month should not be given high assessment scores. Consider using a proportionate scale to reward employees who give more/work harder.








