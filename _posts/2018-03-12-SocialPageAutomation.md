---
layout: post
title: Social Media Page Automation
subtitle: automate url visits to increase profile visibility
bigimg: /img/SocialPageAuto.png
tags: [Social Media, Automation, Selenium, python]
---

I am **not** a huge fan of social media, but I understand that it can definitely be used to help your profile.

A friend of mine created a simple script which would go through urls of notable people in an automated fashion to help increase their profile views.

I really liked the concept of this, as it could help me bolster my social media accounts. Accounts which I have been neglecting for so long! 

The script I wrote uses Python, Selenium and Chrome.

It opens a session of Chrome, logs into a social media page, iterates through saved urls in a CSV file, then logs out and ends the session.


#### Fraud Factors Considered in Development
Many sites will disable accounts if they detect fraud or automation
1. Too many profile views within a set period 
2. Visiting urls in rapid succession, too fast for humans
3. Not scrolling through the page


#### Features:
Design features to address aforementioned issues
1. CSV file was limited to below 200 urls
2. User specified minimum time interval, script will choose a random time between Min and Max (Min + 30 seconds)  
3. Selenium action to scroll down random interval between 600 and 1280 pixels
4. Log-in and Log-out is automatic


#### Future Consideration:
Features on my wish list
1. Randomized iteration of CSV file urls
2. Auto Scrape urls to Update CSV files 
3. Add Keyword browsing to site for associations
