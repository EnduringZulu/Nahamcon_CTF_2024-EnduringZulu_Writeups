# NahamCon CTF 2024 - WriteUps

This is all challenges that I solved.
![Certificates](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/baaf42a68fa2751d138b6b05211ccd2a2497465589d9998bca94617975a4e4a5.png)

## Category that I solved

Warmups - All

Web - 2

# Warmups

## Twine

Google tells me that twine means: "strong thread or string consisting of two or more strands of hemp, cotton, or nylon twisted together."

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled.png)

## Uriel

Uriel was browsing the web and he saw this big long blob of text in his address bar! He was telling me about it but I don't remember everything he said... I think he mentioned something like "it happened twice?"

```
%25%36%36%25%36%63%25%36%31%25%36%37%25%37%62%25%33%38%25%36%35%25%36%36%25%36%35%25%36%32%25%33%36%25%33%36%25%36%31%25%33%37%25%33%31%25%33%39%25%36%32%25%33%37%25%33%35%25%36%31%25%33%34%25%36%32%25%33%37%25%36%33%25%33%36%25%33%33%25%33%34%25%36%34%25%33%38%25%33%38%25%33%35%25%33%37%25%33%38%25%33%38%25%36%34%25%36%36%25%36%33%25%37%64
```

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%201.png)

It’s URL encode!!!

## Technical Support

Want to join the party of GIFs, memes and emoji shenanigans? Or just want to ask a question for technical support regarding any challenges in the CTF?

This CTF uses support tickets to help handle requests. If you need assistance, please create a ticket with the #ctf-open-ticket channel. You do not need to direct message any CTF organizers or facilitators, they will just tell you to open a ticket. You might find a flag in the ticket channel, though!

Just join a discord lol

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%202.png)

## Read The Rules

Rules

We don't want to have to enforce restrictions on you, but there are a few things we would like to politely ask you not to do:

```
Please do not attack the competition infrastructure or other players. The challenges are your targets. That's it.
You do not need to use automated scanners like sqlmap, DirBuster, nmap, Metasploit, nikto or others. Please do not use them against the challenges.
Please do not brute-force flags.
Please do not share flags with other players, or explicitly and deliberately cheat.
Please do not blatantly ask for hints. The proper to way to ask for help is to explain what you have tried and showcase(in a direct message) what errors or output you may have.

```

Flag Format

Flags for this competition will follow the format: flag\{[0-9a-f]{32}\}. That means a `flag{}` wrapper with what looks like an MD5 hash inside the curly braces. If you look closely, you can even find a flag on this page!
Support

For admin support in the case of any technical issues, please join the NahamSec Discord server.

You should find a #ctf-general channel in the NahamCon 2024 category and direct your questions there. When your question requires discussing a specific challenge, please direct message one of the challenge authors as noted in the challenge description.

Flag in comments

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%203.png)

## QRRRRRRRR

Wait a second, they made QR codes longer!?!

So… it’s 810x150 Found!!! It’s a rMQR code.

Link: https://github.com/OUDON/rmqrcode-python

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%204.png)

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%205.png)

Download on your mobile and scan.

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%206.png)

## EICAR

What is the MD5 hash of this file?

Wrap the hexadecimal value in the flag{ prefix and { suffix to match the standard flag format.

Note, your antivirus engine might flag this file -- don't worry, I promise it's not malware :)

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%207.png)

## That's Not My Base

Everyone knows about Base64, but do you know about this one?

(Remember, the flag format starts with flag{!)

```
F#S<YRXdP0Fd=,%J4c$Ph7XV(gF/*]%C4B<qlH+%3xGHo)\
```

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%208.png)

## Copypasta

You know those funny Internet messages that everybody likes to copy and paste? Yeah....

Turns out they make a good Warmups CTF challenge, too!

Press the Start button on the top-right to begin this challenge.

just `nc` and copy that to somewhere else lol

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%209.png)

# Web

## IDoor

It's Apple's latest innovation, the "iDoor!" ... well, it is basically the Ring Doorbell camera, but the iDoor offers a web-based browser to monitor your camera, and super secure using ultimate cryptography with even SHA256 hashing algorithms to protect customers! Don't even think about snooping on other people's cameras!!

Press the Start button on the top-right to begin this challenge.

It seems like the vulnerabilities of this one is IDOR.

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%2010.png)

Find the hash from the url:

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%2011.png)

Generate SHA256 using python

```python
import hashlib

for i in range(0,20 + 1):
    # Convert the number to a string and encode it to bytes
    input_string = str(i).encode()
    
    # Create a SHA-256 hash object
    sha256_hash = hashlib.sha256()
    
    # Update the hash object with the bytes of the string
    sha256_hash.update(input_string)
    
    # Get the hexadecimal representation of the hash
    hash_hex = sha256_hash.hexdigest()
    
    print(hash_hex)

```

Put it in txt file and run the Burp Suite using Intruder

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%2012.png)

Start attack!!!

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%2013.png)

Found!! It’s ID=0 lol

## All About Robots

Oh wow! Now you can learn all about robots, with our latest web service, All About Robots!!

Press the Start button on the top-right to begin this challenge.

Special thank you to YesWeHack for sponsoring the NahamCon 2024 CTF! This category is dedicated to them as a token of gratitude.
YesWeHack

Based on the title of this challenges, I’m 90% sure that maybe it’s robots.txt lol

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%2014.png)

Copy the Disallow path and try it:

![Untitled](NahamCon%20CTF%202024%20-%20WriteUps%20811f6ee20ca94aa9b026881988e12d91/Untitled%2015.png)