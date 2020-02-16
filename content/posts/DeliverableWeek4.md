---
title: 'Deliverable - Mr Robot CTF'
date: 2020-02-16
draft: false
featuredImg: ""
---
************
# Introduction

Mr Robot is a capture the flag based box which I chose to complete as my deliverable this week, it was done through Try Hack Me which is accessible [here](https://tryhackme.com/room/mrrobot "LFI Presentation video"), when each flag is found it needs to be marked through Try Hack Me system. Moreover Try Hack Me runs through openvpn to access the box.


# Write Up

The first step within any penetration test is to enumerate, as such I had an IP address given from Try Hack Me, I chose to use nmap which is a network scanner and will allow me to discover the services that exist within the IP tested against. I initially ran nmap with flags with a safe script, as depicted below;

       nmap -sV -sC IP


Unfortunately I ran into errors, so I chose to run nmap without any flags, this worked and showed 2 open ports 80 and 443, both of which are internet facing website ports for http and https protocols respectively, as seen in the image below.
![nmap scan](/nmap.PNG)


Alas, since the website ports are open I chose to visit the website it took a while to load, my first instinct led me to check the page source as if the page took a long time to render I thought the Javascript files might not be configured properly, and there could be a possibly key through there. But through meticulously checking the source code and also going through contents in inspect element I couldn't find anything on the website which might have given me hints, for capturing the first flag.

Next I chose to enumerate all the directories contained within the website, I did this using goBuster. I used the following command;

       gobuster dir -u http://10.10.78.177 -w /usr/share/wordlists/dirbuster/directory-list-2.3-small.txt -o MrRobotBuster.txt

This then outputted the following;
![goBuster scan](/robot.PNG)

As such I went through each file as gobuster was presenting them (brute force was a considerable amount of time). Some of the file’s led to very valuable information such as the wp-login directory (which let me know wordpress was running, more on this for capturing the next flag) whilst other file's gave little to no of value (such as readme or rss), but when opening robots my first break came, in the structure of a web crawler (robots.txt), two files were exposed, as seen below;

![goBuster output](/crawler.PNG)

Now all I had to do is search ‘key-1-of-3.txt’ in the URL and my key was enumerated, and ended up being correct when i entered the key into Try Hack Me, the key is shown below;

![goBuster output](/key1robot.PNG)

*******************************

With the first flag successfully captured I could now move on and focus on capturing the second flag. From the /robots page I decided to install the dictionary file contained within called fsocity.dic. Additionally the previous mentioned gobuster files output had a /wp-login directory, meaning wordpress was used as a website builder. Accessing this page led me to the login prompt just like normal wordpress websites, as shown below;

![alt text](/wperr.PNG)

Seeing a login prompt the first thing I tried using was an SQL Injection to access the website such as; (‘ OR 1=1--), I then tried doing some common usernames such as admin but still the login in prompt was not budding. After a long time trying and researching wordpress
vulnerabilities for login’s (i.e LFI ?author=1), I concluded the only way forward would be to use a brute force type attack on the login page.

Through the mention of my studio facilitator jason he pointed me to use wpscan, though I did not have a thorough understanding of how the scan works and kept running into forbidden pages as so;


![alt text](/scanerr.PNG)

Ultimately I had to fall back on hydra which is another login cracker but unlike wpscan that specializes in wordpress vulnerabilities it specialised in login cracking for many protocols. Through studying hydra and researching online examples of hydra being used against wordpress logins I ended up also having to use burpsuite to retain the post-form parameter, as shown below;


![alt text](/wpburp.PNG)

This was used as a parameter in hydra, moreover the dictionary obtained was now going to be used as the list of usernames for hydra to test with, the command entered in as below;


       hydra -L ./MrRobot/fdocity.dic -p testpass 10.10.200.175 http-post-form ‘/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log+In:F=Invalid username’




This produced the following results and gave a hut for a login name called Elliot, as seen below;

![alt text](/hydra.PNG)


Now when entering the username as Elliot in the username prompt instead of an error prompt I receive that the password is incorrect for the user Elloit, reaffirming that the username Elliot is a valid username for the web page, this is displayed below;

![alt text](/elliot.PNG)


Now that the username is confirmed I figured that I would retry to use wpscan, as hydra took too long. Additionally I chose to shorten down the dictionary file by piping it through uniq so that no duplicate entries exist (suggested by mentor to use uniq). As such I used the following command;

# Location
       wpscan --url http://10.10.30.145 --passwords ./newsort.dic --usernames elliot

And it gave me a hit for the password as seen below;
![alt text](/epass.PNG)

Finally I was into wordpress after a very long time :). Through reading online about wordpress vulnerabilities I thought the best way to attack would be to upload a reverse shell script as a plugin and listen and try and connect but unfortunately, the webpage would not let me upload plugins

![alt text](/plugin.PNG)

After going through the whole page MANY, MANY i was able to see that a php file existed in the theme, specifically it was a 404.php template that existed, so I knew that I also could possibly  upload a reverse shell there. Researching online a reverse shell existed on my kali system under the file;

# Location
       /usr/share/webshells/php/php-reverse-shell.php

I then added the file as below and edited the IP and port number respectively to my own settings and updated the file.

![alt text](/404.PNG)

Now that I’ve updated the 404 file, I set netcat (nc) to listen to the website this is fundamental in a reverse shell (we act as the listener). As such I wrote the command;

# Location
       nc -lvp 2170

Once my listener was set on my specified port; 2170 (best suburb postcode), all I needed to do was enter a URL that would exist i.e(/thisfiledirwontexist), and the 404 reverse shell I uploaded will go to work. Once the 404 shell i uploaded works the listen set will connect, as displayed below;

![alt text](/2170.PNG)

As such currently logged in as daemon, we only have a low privilege shell, to escalate our shell I used a python script which escalate me (thanks jason), as seen below;

![alt text](/py.PNG)

Now with access to a higher privileged shell I went into the home folder and saw a directory called robot which I went into, contained the key, as shown;

![alt text](/cd.PNG)

But the only problem was that I couldn’t open the key file as the owner was ‘robot’, as depicted below;

![alt text](/nope.PNG)

Though i was able to read the contents of the password.raw-md5 file, is outputted a hash value as shown below, though I quickly went online and found a md5 hash converter and pated the value it write the alphabet from a-z as the plaintext

![alt text](/md5.PNG)

So i then su into the robot user and entered the alphabet character as the online tool cracked and I had access, i was able to read the second key and its displayed as below. YAYYYYYYYY!!

![alt text](/new.PNG)

*************************

# Location
       mihailo@residence:~$ pwd
       C:/Australia/NewSouthWales
