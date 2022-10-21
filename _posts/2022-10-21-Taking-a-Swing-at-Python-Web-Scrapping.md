---
layout: post
title:  "Taking a Swing at Python Web Scrapping"
date:   2022-10-21
author: Rachel Miles
description: Using Python to web scrape and create a dataset of all the MLB Player's salaries, positions, and status. 
image: /assets/images/joshua-peacock-aMuXhFkbxEw-unsplash.jpg
---
I've liked baseball since I was old enough to talk.

I thought going to baseball games was great. My Mom would take me to the Dodgers games and we'd eat hot dogs and sing "take me out to the ball game" and I'd get to stay up past 9:00pm. I was the kid living the dream and I was loving it. 

Unfortunately, I can't really go to games all that any more, so I decided if I can't go and enjoy the baseball magic at a game, why not bring the baseball magic into my life? What's the point of learning statistics if I can't use them to overanalyze something I really enjoy? So the journey began, and oh boy, I didn't think it was going to be this hard. 

## Finding the data
Finding the data itself was the easiest part. I've always wanted to know how much players made and how stats like RBI (Runs Batted In), HR (Home Runs), and what position they played affected what they earned. Since I was going to be doing a data analysis project, I decided I was going to answer this question definitively. 

Thus began the hunt. 

At first I thought I was going to have to scrape those stats off each team website (which would've been tedious and extremely stress inducing), but the problem was that most team websites don't tend to publicize how much their players make. That was supposed to be my dependent variable, and the fact that they didn't have it made that avenue rather useless. 

So I kept looking. I eventually found [spotrac.com](https://www.https://www.spotrac.com/)  and they had the variables I actually wanted, or at least position and salary, the two most important ones. They also have data on other sports leagues like the NBA, NHL, NFL, so if you're looking for data like that, it's an extremely useful website. 

I had found where my data was, now I had to get it off the web and into a file I could actually use. 


## Scraping the data
I would be saying that this was the hardest part, but I would be lying to you. It was the longest part, but not the hardest.

I had found my dataset! Hooray! 

Once I thought that this data would be possible to scrape, I went to the robots.txt to make sure it was ethically acceptable to scrape. According to robots.txt and from TOS on the website, it was okay. To be honest, I'm not a legal expert, but since most of the information found in the table is already public, it's most likely fine. 

Cool, so it's technically and ethically possible. Now it's time for the scraping.

The hardest part of this was setting up all the for loops to both scrape the tables and the data. Unfortunately I couldn't do a read_html on a page and get all the data because every dataset was on a different page. And being the tryhard that I am, I had to get every baseball team. All 30. So you can imagine how much time that to set up a for loop for getting each link to each page, read_html-ing each page, and then concating the first table in each page together to get a list of all the active players.

Why only the first table? I didn't feel it was necessary to include injured players or retired players or whatever have you. My dataset ended up being about 4100 entries long, and since those players made up a small subset of population, I was confident I would still get accurate results without those entries.

So I got a table which looked something like this:
![Test image](https://raw.githubusercontent.com/rmiles7720/stat386-projects/main/assets/images/Blogpic1.png)



Which is wonderful! I got a dataframe! 

However, as we've already established, that's not good enough. My table needed to be the best, cleanest table I had ever seen. I wouldn't accept anything less. So, it was on to the data cleaning phase. 


## Cleaning the data
I would say this was the hardest part. I had to get rid of serveral variables, convert the table from wide to long, and make sure that the players names were in the same first column. 

As you can see above, the dataframe I got had multiple columns of active players. Why you may ask? Because different teams have diffent numbers of players. Some have 31, some have 30, some have 27, and some have 842 for some reason? Your guess is as good as mine. 

I used pd.melt to make the table go from wide to long and then deleted the resulting column that listed out the number of active players the team had. Then, I switched the columns around so the name column would be first and dropped all the columns I didn't want. I ended up only keeping name, age, position, status, and adjusted salary, saince those were the variables I actually cared about. 

My table ended up turning out like this:

![Test image](https://raw.githubusercontent.com/rmiles7720/stat386-projects/main/assets/images/Blogpic2.png)

You might be wondering why it says it goes up to 26000 entries. It still goes up to 4100; the indexes didn't change when I dropped all the null values in the previous dataframe to get this one. 


## Conclusion
It was a lot of work, but I managed to clean and make a dataset I really liked. Web scrapping isn't easy, but it's definitely worth it!

If you are interested in the nitty gritty of each step or my resulting data, I would recommend going to my repositiory: https://github.com/rmiles7720/mlbPayrollData 

I have all the code I used, the resulting csv, and an intermediary file since web scrapping 30 teams' data off of multiple webpages takes a long time. 

Here's where I found all the MLB data I could possibly want: [Spotrac MLB Data](https://www.spotrac.com/mlb/)

Happy coding!
