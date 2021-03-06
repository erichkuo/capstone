# Technical Report - Vital Statistics of Professional Athletes

## Problem Statement
### What impact does a career in professional sports have on the life expectancy of an athlete?

More specifically:
- Do different sports have different levels of impact on athletes' life expectancies?
- Are life expectancies further affected by the length of the playing career, the number of games played, or the positions they played?
- Can I build a model that predicts how many players will die in a given year, based on vital statistics of the general population?
- How do the distribution of athletes' ages at death compare to that of the general population? 

## Data Collection

Data has been collected for athletes who have played professional baseball, football, basketball, and hockey. These data were collected from the following sports reference websites:
- [Baseball reference](https://baseball-reference.com)
- [Pro Football Reference](https://pro-football-reference.com)
- [Pro Basketball Reference](https://basketball-reference.com)
- [Hockey Reference](https://hockey-reference.com)

Data collecting from each site included 
- birth years and dates
- death years and dates
- length of career
- number of games played
- year of start and end of career

For baseball and football, height and weight were collected from individual pages. For basketball, country of birth was collected, though it was not used in analysis.

In addition, data was also gathered for life expectancies of the general population. Sources include:
- [Social Security Administration](https://www.ssa.gov/oact/STATS/table4c6.html)
- CDC Live Births in the US

## Analysis and Modeling

### Annual Athlete Deaths

Expected number of athlete deaths were computed for each league. These numbers were computed based on number of players born in a year, and percentages of males of a certain age expected to die in a given year. Here is a sample figure for NBA players, plotted against actual number of deaths.

![](https://github.com/erichkuo/capstone/blob/master/visuals/NBA_expected_deaths.png)

Similar computations were made for players in other leagues. The expected numbers of deaths actually tended to overestimate the actual numbers for the other leagues.

### Distribution of Ages at Death

A/B testing was used to determine whether the distribution of ages of athletes' deaths were comparable to that of the general population of American males. Only baseball seems to have a different distribuion from the American population. Indeed, one graph indicates that baseball players have the highest life expectancy.

![Average Age at death](https://github.com/erichkuo/capstone/blob/master/visuals/average_age_at_death.png)

### Predicting if an Athlete is Still Alive

Classification was attempted to determine whether a baseball or football player born between 1930 and 1945 is still alive. Unfortunately, none of the classification models worked successfully. Even including height and weight of players didn't improve anything. Indeed, when one examines correlation between features such as length of career, number of games played, height and weight against age at death or player is alive or dead, one sees no correlation.

![MLB no correlation](https://github.com/erichkuo/capstone/blob/master/visuals/mlb_correlation_heatmap.png)

Then I looked at how age at death varies with length of career:

![Age At Death Versus Experience](https://github.com/erichkuo/capstone/blob/master/visuals/age_versus_experience.png)

## Conclusion

Ultimately, one cannot conclude that a career in professional sports adversely affects the life expectancy of an athlete. If anything, Major League Baseball players seem to live longer lives than the general population. Expected numbers of athlete deaths tended to exceed actual numbers of deaths of baseball, football, and hockey players. Finally, there is no correlation between the length of a career or (for baseball and football players) even the physical dimensions of an athlete with how long an athlete lives or whether an athlete is still alive.

## Future steps

Should this project get revisited in the future, some considerations we might make include:
- How correlated is the country of birth to the life expectancy of an athlete?
- Will other sports, including tennis, golf, or auto racing show any differences (or lack thereof) in life expectancy either?
- How might a more accurate model be built for predicting annual athlete deaths?

