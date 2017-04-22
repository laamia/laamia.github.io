---
layout: post
title:  "Glassdoor Scraper"
date:   2017-04-21 21:17:45 -0400
---


![](https://press-content.glassdoor.com/app/uploads/sites/2/2015/04/GD-logo-green-on-white-01.jpg)

Why are we all enrolled in this class?? Because we want jobs as Software Engineers! Now, whether you work for yourself or for someone else, that's up to you. For those of us that are looking for opportunities, Glassdoor is an awesome place to get good data (although it's pretty scattered) about job opportunities. I built a scraper that gives you the bare essential details about each job and the company that it's with.

My program has 3 classes (cli.rb, scraper.rb, and job.rb). 
* The CLI class provides all the prompts and input options for the interface. It also has some functions that display job and job details
* The Scraper class pulls data from the Glassdoor website
* The Job class defines jobs and their attributes and allows you to retrieve attributes

My biggest challenge was dealing with the fact that it takes 2 clicks to get to company details. Basically I had to open 2 different pages before I could get to the data I actually wanted. As a result, I had to put some of my scraping code in the Job class. If I were to improve this. I would figure out a way to move all scraping code into the Scraper class and generalize it a bit more.

My next largest challenge was pushing to github. I kept getting the following error every time I add, committed, and did git push origin master.
```
error: src refspec master does not match any.                                                                                          
error: failed to push some refs to 'git@github.com:laamia/glassdoor_scraper.git
```
Unfortunately, I was able to get 0 help in this department :-/ So still stuck on this.

