---
title: 'Week 4 Reflection'
date: 2020-02-16
draft: false
featuredImg: ""
---
************
## *SLO 1)*
> ### Engage with stakeholders to identify a problem or scope a defined problem.

This week the studio mentors served as the stakeholders, as no external stakeholder came to the university to present nor did I personally go and find any cybersecurity meetings to attend. As such this week's focus was upon penetration testing of a virtual machine to become the root user within a system, which is also known as ‘boot2root’. Within the class, studio mentor Jason ran through an example penetration testing demonstration against a vulnerable machine called wakanda, where he showed his thinking pattern to progress on through the machine. This included enumerating performing reconnaissance to exploiting vulnerabilities found from this process, all of which feeds back to the anatomy of a pen testing cycle,  that keeps getting referred to within the slides and as depicted below;



/anatomy.PNG
![Pen Test loop](/anatomy.PNG)


Watching the demonstration allowed me to gauge how the penetration testing thinking process is developed and showed me that enumerating (info gathering stage), was critical for any penetration tester and that to progress through to becoming a root user, important information gathered was needed. This was highlighted in the demonstration when Jason found a vulnerability within the antivirus.py file that existed within the system which allowed for him to eventually edit the file and also it re-initialized every 300 seconds, which theoretically allowed him to upload a reverse shell. Witnessing this really allowed me to understand that within the industry security teams cannot afford to misconfigure any little piece of information, as a small error within the system (i.e. allowing file to upload every 300 seconds) could end up having devastating impacts and possibly exposing a companies whole system.


*****************
## *SLO 2)*

> ### Apply design and systems thinking to respond to a defined or newly identified problem.

This week each class member within the studio had a deliverable, which was to gain root access to a vulnerable machine. This week I chose to do the Mr Robot CTF, as Max had said it was a great vulnerable machine to use.

Personally this week deliverable was a ‘mixed bag’ as some content I understood and have somewhat become very familiar with the tools needed to obtain a certain results, whilst I also have difficulties with other content and tools I haven't used nor understand too well, and become really stuck. With this in mind I had to read upon A LOT of documentation and watched youtube demonstrations this week for my deliverable as I didn't understand; how brute force login tools worked, understanding of what a reverse shell is and how to use it, and understanding how CMS work and especially the vulnerabilities that can be exploited within wordpress. One such examples has to be on the tool hydra, which is a brute force login cracker working on many different protocols, as such I found the manual pages very confusing, and more so having to implement the http request form with hydra to use the brute force really confused me as I haven't mastered the use of burp suite. As such watching the youtube video down below allowed me to mimic the tool and manipulate it for my purpose of using it in wordpress, and also showed me how to use burp suite to get the information needed as a parameter to use in hydra;

![Hydra](/htube.PNG)

Another issue I had this week was with my VM image, which unfortunately had broken down and meant i lost all the valuable files/screenshots I stored and I didnt have a backup. As of now I will make snapshots of the VM so this can’t not have the same effect as this time, and as i purchased an external SSD this problem shouldn’t be an issue for next time.


*****************
## *SLO 3)*

> ### Apply technical skills to develop, model and/or evaluate designs.

Like previous weeks, I've applied my technical skill well and throughout the studio within class time and outside of it too. This week was mostly dedicated to my deliverable where I applied most a lot of technical skills to inevitably become the root user, which can be found; *[here](https://mikik.me/posts/deliverableweek4/)*.

Apart from the deliverable I’ve also applied my skills with other Try Hack Me Challenges in my own time such as; vulnversity and advent of cyber walkthroughs which teach how to use tools and I’ve have to apply myself to complete the questions/tasks at hand. Moreover as briefly mentioned in SLO1, I also dedicated myself this week to implementing the anatomy of pen test cycle, as when completing my deliverable I wanted to implement techniques and design thinking as would professional penetration testers to really get a sense of implementing a proper attack vector.




*****************
# *SLO 4)*

> ### Demonstrate effective collaboration and communication skills

Both studio lessons this week included a standup meeting, where alongside other class members I communicated my thoughts and opinions of how I was progressing. This really allowed me to self-reflect on my current goals and really gauge where I was with my penetration testing abilities compared to other class members.

I also came in on the Wednesday drop-in session, in which I was able to collaborate on completing basic pen testing 1, and this talking with others allowed me to realize i was one vital step (using john) to break the contents within /etc/passwd and /etc/shadow and find the plaintext password.

Additionally throughout the week I had also communicated with studio mentor Jason about my deliverable, in which he helped guide me down the correct direction.

![Jason](/json.PNG)

*****************
# *SLO 5)*

> ### Conduct critical self, peer, and group review and performance evaluation.

In comparison to my previous three week, this current week has not been efficient (especially when compared to last week). In terms of content absorbed and learnt I felt it was at the same level as previous weeks, but it was my external studies for this subject, (such as pursuing the Security+ to absorb content) which was frankly non existent. Though I had planned out a timetable for completing all activities I found myself only doing my deliverable and as when I had different activities planned I just kept progressing through with doing my deliverable. I believe this comes down to two main causes; the first being underestimating the time needed to complete the deliverable task which in itself is a time management issue and secondly not sticking to my timetable and doing all planned content within the timetable, as such this made my performance lack when evaluated against last week.  

My peers within the studio this week have been excellent, with most feeding information from each other and also being a helpful hand when others are stuck on a task.

Personally this week I’ve fallen short of the goal i set for myself this past week, as such I’m going to try and make time to complete all goals I have set for this subject by making a more flexible timetable to adjust for activities which may need more time.
