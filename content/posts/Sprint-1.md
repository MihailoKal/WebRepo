---
title: 'Sprint 1'
date: 2020-01-25T12:29:41+08:00
draft: false
featuredImg: ""
---

### *Question 1)* Engage with stakeholders to identify a problem or scope a defined problem.

For our first submission we were specifically instructed to create a static website, as in doing so it allowed me to question the reasoning for implementing a static website versus a common website generator. Through research and engagement with studio facilitators I’ve come to understand that static websites are well respected in the cybersecurity industry as they are very secure. They are more secure because static sites do not have any databases that can be compromised by attackers and also when a static site is attacked it doesn't have any important information that can be used by the attacker, hence why static sites are well respected as a blog within cybersecurity.


### *Question 2)* Apply design and systems thinking to respond to a defined or newly identified problem.

During my studio most of the content was fairly new to me, ranging from using git (version control system) to learning how repositories work. With this in mind I went online to learn this new content and started to read documentation on how to use git and also how github and repositories worked to host my website. Another problem within creating my static site that was that I had installed Hugo(static web generator) through a package management tool and allowed the install in my System32 folder, which was a massive issue as a user cannot nor should write to the System32 folder which contains files vital to the windows operating system. Through reading Hugo’s documentation and also watching youtube tutorials i realised that my Hugo download had ended up in System32 folder and I quickly copied it to another directory. The last problem was that I was unfamiliar with windows powershell which made me spend a lot on just trying to install a hugo theme, as depicted below;

![alt text](/Capture.PNG)

I solved this by using the git bash which allowed me to use Linux commands that I felt comfortable with to add themes and edit files much easier.

### *Question 3)* Apply technical skills to develop, model and/or evaluate designs.

Creating a static website with markdown, was basic and an online page helped me grasp how to use markdown with a quick read. But understanding where to place content, images and how to place them in certain positions for the best user experience of the website proved to be challenging. Added to this the selected theme would also at times make the website look unusual and required me to evaluate the themes config file to edit.    


### *Question 4)* Demonstrate effective collaboration and communication skills

Collaboration and communication were vital in allowing me to get my website to work properly as it was meant to. This was paramount as when I deployed my website in the very first instance the CSS did not work and displayed the website as soon below;

![alt text](/Web.png)

The issue was simple but I couldn't seem to pinpoint the error, through communicating with one of my studio mentors I was able to understand the issue was within my configuration file, which didn't make the CSS display as it should’ve, down below was the personal teams chat I had which after implementing the consideration made the CSS work and display the website as you see it now.  

![alt text](/PM.PNG)
