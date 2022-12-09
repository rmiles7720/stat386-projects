---
layout: post
title:  "The Story with Baseball Salaries"
date:   2022-12-08
author: Rachel Miles
description: Telling the Data Story of MLB Players Positions and Their Salaries
image: /assets/images/blog-4-photo.jpg
---

Data can tell many stories. There's so much information one dataset has, it can be difficult to explain results in a clear and concise way. There's so much to try and process, and like all good stories, there's a lot of time, effort, and editing that goes into it. 

The data story I will be telling today is that of how MLB Players' salaries relate to the position they play. Is there a significant relationship between the two? Do players get paid more depending on what position they play?

If you're interested in how I got this data or the intial EDA of this data I would recommend following these links: [Web Scraping](https://rmiles7720.github.io/stat386-projects/2022/11/18/Taking-a-Swing-at-Python-Web-Scrapping.html) and [EDA](https://rmiles7720.github.io/stat386-projects/2022/11/18/Exploring-Data-with-the-Pros-EDA-of-Pro-Baseball-Players-Salaries.html).

Now on to our Data Story!

## Data Story

The best way to describe this data is through boxplots. The following collection of boxplots show the means and spread of player's salary by position. Also, the boxplots show how big the spread is between the lowest salaries and highest salaries for each position.

The following plot doesn't include outliers. Why not? Because there were a lot, and believe me, I'm saving your eyes from having to look at too many black dots. Also, the outliers tended to concentrate around the ends of the boxplots anyway, so the exclusion of them doesn't take away from our findings. You'll see why in a moment. 

![Test Image](https://raw.githubusercontent.com/rmiles7720/stat386-projects/main/assets/images/Blog4Bigger.png)

As you can see, there's a *lot* of spread. The spread seems to be higher for pitchers, designated hitters, outfielders, and third/first basemen. This was another reason why I didn't include outliers, since most fell into the range of $0 to $2,500,000. You do have your Clayton Kershaws and Albert Pujols who are Vets to the game and bringing in around $20,000,000 a year, but that's rare, even in the major leagues.

So, there is bigger spread on some of the positions, but that also means the means are higher. there's higher chance to reach the $3,000,000 salary mark in those higher spread positions than the lower ones. At least, that's what this figure would be telling us. I'm inclined to agree.

## Analysis of Variance

Just to corroborate my boxplots, I performed a simple ANOVA on our dataset. With a significance level of 0.05, the p-vlaue of there being no relationship between Salary and Player position is 9.34^-9. This is extremely significant. With that p-value, we can reject the idea that there is no relationship between Slary and Player position. 

To be triple sure, I made sure that Arbitration status, (how much power you have when negotiating your contract. It is a helpful measure of how long a player has been in the MLB. Players who have been in the MLB the longest have Veteran status, and the list goes down from Arb-4 down to Pre-Arb), was not a confounding factor. Arbitration Status is extremely significant (which isn't suprising), but it doesn't negate the significance of a Player's position in determining salary. 

## Conclusion

Thank you for coming on this journey with me! If you're interesting in my code, or where you can find this data to do some analysis yourself, you can find that [here](https://github.com/rmiles7720/mlbPayrollData)

Happy Coding!
