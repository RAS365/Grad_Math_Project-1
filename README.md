# Grad_Math_Project-1 - Is someone likely to catch COVID just because they vote for a certain party? or because they are better educated?

### This file is a project log containing my journey from the start to the end. Enjoy!

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
    - Assuming that the people of the age group 18+ are solely responsible for the covid infection behaviour. This assumption would negate the requirement of scaling the covid infection data with the 18+ population. 
    

Another, much more significant issue popped up:
- The data available for COVID infections and the voter orientation are for 67 counties while that for education are for only 39 counties. I tried going to data.census.gov to obtain better data, but I could not find any which had all the 67 counties in it. So, I am left with no choice but to assume that these 39 counties are representative of the entirety of the state.


\rant
I HOPE THAT NO ONE HAS TO EVER SPEND A BIG CHUNK OF THEIR TIME CHANGING THE DATA TYPE OF CELLS IN THEIR EXCEL FILES FROM TEXT TO NUMBERS. I HAVE NO CLUE WHY ANYONE WOULD STORE NUMERICAL DATA AS TEXTS.

I understood why cleaning up data is such a huge task. The entirety of my weekend was spent cleaning up the data. What a way to celebrate Diwali.

\rant_end

I ended up with several excel sheets and a few different ipynb files dedicated to each set of data. These will be uploaded to the repository as well.


The linear regression shows that y(covid infections) and x2(political orientation) has a |t-statistic| of 0.653, i.e., we can't neglect the null hypothesis of the coefficient of x2 being 0. x2 has been discretized to 0 and 1 to make things more convenient. Now, a more continuous approach would be tried to see if that makes a difference.

Adding the data from another state made a significant difference. Now, x2 has a |t-statistic| of with a p-value of 0.111, which is much, much better than before. Ohio was chosen as the second state.

Well, adding data from a third state changed the situation altogether. Now, x2 has a |t-statistic| of with a p-value of 0.859, which is leads me to think that for these three states, voter orientation isn't really a factor. New Jersey was chosen as the third state.


### I LOOKED AT THE DEATHS DATA AND WOW. 
I came looking for copper, but I found gold instead.

Covid death rate has a strong correlation with the average education level of a county. The p-value for the null hypothesis that the coefficient of x2 is not zero is 0.124, which is the best so far for the voter data.

here are some images supporting my results-

- COVID infections data:

![OLS results for y vs x1 and x2](/Images/OLS y no interactions.png)

![OLS results for y vs x1 and x2 with interactions](/Images/OLS y with interactions.png)

- COVID death data:

![OLS results for y2 vs x1 and x2](/Images/OLS y2 no interactions.png)

![OLS results for y2 vs x1 and x2 with interactions](/Images/OLS y2 with interactions.png)


