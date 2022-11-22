---
layout: post
title: Exploring Data with the Pros: EDA of Pro Baseball Players Salaries
date:   2022-11-18
author: Rachel Miles
description: An Exploratory Data Analysis of MLB Payroll data for 2022!
image: 
---

Have you ever wondered how much Pro Baseball Players get paid? Have you ever wondered if what position has effected how much make? Or how old they are? Or how long they've been in the league? 

Well I have. This is an Exploratory Data Analysis of data for every Active Player in the MLB in 2022. The data was taken from spotrac.com, a website which compiles professional athletes salaries and stats. You can find a brief overview of both how I got this data [here](https://rmiles7720.github.io/stat386-projects/2022/10/21/Taking-a-Swing-at-Python-Web-Scrapping.html) and the dataset itself in [this github repository](https://github.com/rmiles7720/mlbPayrollData). We can look at the data through the use of data visualizations to determine if any of those factors are worth a deeper look. This explortory data analysis will be a precursor to a statistical analysis to determine if any of the factors above are statistically significant.

## Let's look at the data!

Since a large amount of this data is categorical (by design), we have to get a little creative with how we view the data so we can understand it properly. 


#### Age and Salary
Since age and salary are the only two variables that are numerical, a basic scatterplot is a good place to start. I've plotted both variables as follows, cutting off age at 18 since there aren't any players who are minors. 

![Test Image](https://raw.githubusercontent.com/rmiles7720/stat386-projects/main/assets/images/Scatterplot.png)

It seems that a vast majority of players make less than a million dollars per year despite how old they are. We haven't controlled for any other variables so far, so that might change as we venture further into our analysis. 



#### Age, Salary, and Status
Next I decided to control for Arbitration Status in a correlation table. As I said above, the only two numeric variables are age and salary, so I did have to create a dummy variable to account for Arbitration Status to make this analysis possible. It's not perfect, but it should give us a better idea if status might be affecting age, or even if it is correlated with age.

Note: If you are confused as to what Arbitration Status is, so was I before this project. Arbitration Status is how much power you have when negotiating your contract. It is a helpful measure of how long a player has been in the MLB. Players who have been in the MLB the longest have Veteran status, and the list goes down from Arb-4 down to Pre-Arb.

![Test Image](https://raw.githubusercontent.com/rmiles7720/stat386-projects/main/assets/images/Correlation.png)

It seems there isn't that much correlation between age and salary, which is what would expect based on what we saw in the previous graphic. Status seems to be correlated with age, once again making sense as older players have most likely been in the mlb longer. Salary also seems to be correlated with status, following the idea that the longer you stay in the same career path, the more money you end up making. 



#### Status and Salary 
Since arbitration Status and salary seem to correlated, let's take a look at the statuses themselves to see if there's a possible significant difference between them.

![Test Image](https://raw.githubusercontent.com/rmiles7720/stat386-projects/main/assets/images/ArbitrationVSStatus.png)

Based on these figures, this seems likely! Once again, as stated above, this makes sense. Hopefully I will be able to block on these statuses to determine if there is a significant difference in player's positions by salary, regardless of arbitration status! That seems like it will help my findings be more conclusive!



#### Position and Salary
Now this where it gets interesting! This is what this entire project has been about. The following boxplot will help to show if there are any significant differences in each player's positon and the mean amount of money they make! Let's take a look!

![Test Image](https://raw.githubusercontent.com/rmiles7720/stat386-projects/main/assets/images/PositionVSSalary.png)
Very interesting! I won't say too much more, as most of my statistical analysis will be on this topic, but there seems to be a significant difference, at least based on this figure. 

Once again, I will have to look out for some lurking variables, but this is still good to know!


#### Position, Status, and Salary
![Test Image](https://raw.githubusercontent.com/rmiles7720/stat386-projects/main/assets/images/_______________________)




