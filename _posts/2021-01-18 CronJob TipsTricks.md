---
layout: post
title: Tips and Tricks with Cron Jobs
subtitle: Tips/Tricks based on mistakes made
image: /img/EC2.svg
bigimg: /img/CronJob.png
tags: [EC2, Cron jobs, Dashboard, Linux, Ubuntu]
---

In the process of implementing the cron job, there were some unforeseen difficulties. <br>
I followed the typical steps, but I couldn't figure out why my cron did not execute on time <br>
<br>
*Mistakes were made, doors were slammed, and anger insued* <br>
<br>

If your cron job is not running on time as expected:

## Here is what to check:
1. Check the path
2. Check the timezone
3. Check terminal session

### Check the path
<br>
In the CLI, type 'crontab -l' <br>
This would list the current cron tab file. <br>
Ensure that all of the file paths are correct and that there are no spelling issues! <br>
<br>
If everything is listed as expected, make sure that the specific python environment location is specified. <br>
Use the command: 'which python' <br>
This will list the location of the python version referenced when you use the python command. <br>
Typically the python location would be: /usr/bin/python

### Check the timezone
<br>
When I created the EC2 instance, I set the server location to the East Coast US. <br>
I naturally assumed that the server would automatically set it own timezone to match the server's location. <br>
In the CLI, run 'timedatectl' <br>
<br>
This would list all of the timezones specified on the server. <br>
The command would list: Local time, Universal time, RTC time, Time zone. <br>
If the 'Time zone' is not specified as expected, we can then change it to the desired timezone. <br>
<br>
To change the timezone, lets first look at all available timezones: in the CLI run 'timedatectl list-timezones'. <br>
This would list all timezones. <br>
<br>
Select the desired timezone by running 'sudo timedatectl set-timezone your_time_zone' in the CLI <br>

### Check terminal session
<br>
When I was running the script in the EC2 instance, It kept failing to run overnight. <br>
I learned that the EC2 instances naturally stop running when the terminal is inactive. <br>
We can get around this by creating a terminal within a terminal, so that it would run in the background. <br>


