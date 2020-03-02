---
title: 'Week 1 Reflection'
date: 2020-01-26
draft: false
featuredImg: ""
---

## *SLO 1)*
> ### Engage with stakeholders to identify a problem or scope a defined problem.

For our first submission we were specifically instructed to create a static website, doing this allowed me to question the reasoning for implementing a static website versus a common website generator. Through research online and engagement with studio facilitators I’ve come to understand that static websites are well respected in the cybersecurity industry as they are more secure to an extent. This is because static sites do not hold any valuable information contained in them that an attacker may want to use. Moreover a static website doesn't have any databases or plugins unlike dynamic websites that need to be loaded in, this means an attacker cannot utilise any vulnerabilities within the websites database or plugins to gain valuable information they could be seeking. Hence having a static website is a great first step within the industry and can prove valuable when needing to engage with stakeholders through interviews and networking events as it host as a template of knowledge understood.      

*****************
## *SLO 2)*

> ### Apply design and systems thinking to respond to a defined or newly identified problem.

During my studio most of the content was fairly new to me, ranging from using git (version control system) to learning how repositories work. With this in mind I went online to learn this new content and started to read documentation on how to use git and also how github and repositories worked to host my website. Another problem within creating my static site was that I had installed Hugo(static website generator) through a package management tool and allowed the install in my System32 folder, which was a massive issue as a user cannot nor should not write to the System32 folder which contains files vital to the windows operating system. Through reading Hugo’s documentation and also watching youtube tutorials I ended up realising that my Hugo download had ended up in System32 folder and I quickly copied it over to another directory. Lastly I was unfamiliar with using windows powershell which made me spend a lot of time on just trying to install a hugo theme, as depicted below;

![alt text](/Capture.PNG)

Instead of using windows powershell I started using the git bash, which allowed me to implement Linux commands that I already knew and felt comfortable with. Hence adding themes and editing files became a much easier task.

*****************
## *SLO 3)*

> ### Apply technical skills to develop, model and/or evaluate designs.

Creating a static website with markdown, was basic and an online page helped me grasp how to use markdown with a quick read. But at times the selected theme would make the website behave unusual compared with the demo theme, this required me to edit the configuration file so that content would presents itself as it should. Added to this understanding where to place content, images and how to place them in certain positions for the best user experience of the website proved to be challenging. These issues were all figured and through consistent trial and error and the websites was built and constructed to look as I planned it out.  

*****************
# *SLO 4)*

> ### Demonstrate effective collaboration and communication skills

Collaboration and communication were vital in allowing me to get my website to work. This helpful collaboration is best depicted when I first deployed my website where the CSS did not load and displayed the website as below;

![alt text](/Web.png)

The issue was simple but I couldn't seem to pinpoint the error, through communicating with one of my studio mentors I was able to understand the issue was within my configuration file, which didn't make the CSS display as it should’ve. Down below was the personal teams chat I had with Jason (Studio mentor) which after implementing his consideration made the CSS work and display properly as you see it now.  

![alt text](/PM.PNG)

*****************
# *SLO 5)*

> ### Conduct critical self, peer, and group review and performance evaluation.

Personally I feel as if this week I've given a considerable amount of effort regarding the studio. Upon reflection this week I made a major error with allowing Hugo to install in System32 file, which really slowed down my progress for a while. Next time I should be more careful when using a package manager alongside an application and shouldn’t assume that installation will occur in my program files directory and check where the installation prompt is guiding the file to go.

Another issue I had was with figuring out which theme to use, before choosing the current theme (hermit) I had tried a few themes all of which didn’t seem to configure properly nor had much support documentation within the theme. Hence if I am to change themes in the near future or create a new website for other reasons, I need to make sure that there is a significant amount of documentation which will guide me throughout using the theme and help me troubleshoot errors if they possibly occur. Learning from this next time I can implement a rule of thumb that when attempting to learn something new, to make sure appropriate documentation already exists to help me better understand new content that I may have unfamiliarity with.

Apart from that error I believe that I’ve had a great week in terms of the studio where I learnt how VCS (git) works, which worked to also furthered my understanding of how repositories work.

Performance wise I also believe that I have had a great week as I've finished all assigned work on time, i believe this is attributed to my great time management this week in complete all work required of me.
