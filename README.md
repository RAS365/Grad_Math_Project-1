# Grad_Math_Project-1 - Is someone likely to catch COVID just because they vote for a certain party? or because they are better educated?
A repo  containing all the files for Grad Math project-1
This project is about modeling the relationship between COVID-19 infection rates of counties in PA with the political orientation of the population and their education level.

y -> COVID-19 infection rate of each county

x1 -> political orientation of each county

x2 -> education level of each county

first set of hurdles- 
1. There is no such thing as the political orientation of a county
2. there is no such thing as the education level of a county
3. All the data sets are heavily swayed by the population of that county

Plan to overcome these-
1. Political orientation of a county can be defined as a f(#republican,#democrat,#other,population)
2. Education level of a county can be defined as a function of all the discreet levels of education
3. All the data sets used is to be normalised by the population of each county.

Next hurdle encountered-
- Covid infection data is population wide while the education and voters' orientation data is 18+
  - This can be tackled by the following ways:
    - Assuming that people of years 18- have the same chances of getting infected as those who are 18+. This assumption would allow us to renormalize the covid data that we have to only the 18+ population.
    - Assuming that the people of the age group 18+ are solely responsible for the covid infection behaviour. This assumption would negate the requirement of normalizing the covid infection data with the 18+ population. 

Another, much more significant issue popped up:
- The data available for COVID infections and the voter orientation are for 67 counties while that for education are for only 39 counties. I tried going to data.census.gov to obtain better data, but I could not find any which had all the 67 counties in it. So, I am left with no choice but to assume that these 39 counties are representative of the entirety of the state.
