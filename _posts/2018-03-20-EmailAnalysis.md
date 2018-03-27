---
layout: post
title: Email Compromise Analysis
subtitle: From the trenches
tags: [Blue Team, Analyst, From the trenches]
image: "/img/spam2.jpg"
share-img: "/img/spam2.jpg"
comments: true
---

"This is an automated notice from Exchange Online Protection." Great, that's exactly the type of email everyone wants to see first thing in the morning. This could be usurped in popularity only by a robocall. That would certainly have the potential to get me excited before my first cup of coffee. In any case, according to the alert, it looks like a user's email account is being used to send out spam. Thankfully though, active response parameters have locked down the account and made it unable to send further outbound messages. So lets get cracking and see what's going on!

The first thing we need to do is gather as much information as possible as to the situation that is unfolding. According to the alert 'captainjack@sparrow.com' has been identified as having sent a large volume of outbound spam emails, and his account has been appropriately disabled from sending outbound emails. Let's check his outbound message list and see what we find. In his sent items list we see a large volume of messages with the subject "[RFQ] New Product Order" to various other pirates that he has dealt with in the past. Well that's odd. What does a ship captain know of RFQ product orders, and what dealings would he have with them? Definitely not standard behavior for Jack. Lets drill into the message and examine the contents.

<img src="/img/RFQ.png">

Definitely suspicious. Sending '.htm' files via email is a standard practice for spammers, and this email resembles a general template that can be found out on the web. If there was any doubt that 'captainjack@sparrow.com' was compromised it has now been alleviated. The damage has been done and contained though by locking down the account, so lets grab the file being sent out and run it through a quick analysis on Virus Total (note that here we are not concerned about letting the attacker know that we have his/her sample) and see what we are dealing with. Additionally, lets grab the hash and blacklist it on our network and use it to search across our endpoints to see if any other users were exposed to the file before we had the chance to blacklist it. Thankfully, in the case, no one else was exposed.

<img src="/img/VT.png">

No hits on Virus Total, no problem, we'll analyze it manually out of curiosity. But first lets get captain jack back up and running and kick the attacker out of his account. First things first, force change the users password and give it to him out of band (a phone call will do). Then once the password has been changed, force a logout of his account across all applications and devices, in order to ensure that the attacker is well and truly out. Finally, we'll need to check Jack's email rules in order to make sure that nothing malicious has been added, such as email forwarding. Once this is done, for all intents and purposes the incident has been “remediated”. However the investigation is nowhere near complete. Next the following should be conducted.

- Contact user and see if they remember any suspicious emails with links or attachments, or entering credentials from unusual prompts.
- Find out what their password was, and compare it to commonly compromised passwords or if it is similar to known default passwords.
- Triage where the spam mail was sent from, and where the spammer logged in from, add those IP's to the block list.
- Run incident response on the users machine.
- Revisit alerting rules and active response measures to identify if changes need to occur.
- Optional: Send a bcc email to all addresses the spammer contacted, notifying them not to open their previously received email.
- Optional: Analyze the '.htm' file that was sent out.

Now lets tackle the file analysis part of this incident and load up the '.htm' file in our sandbox environment. Lets start by opening the file in Notepad++ and analyzing the code. 

<img src="/img/htmfile.png">

Immediately we can see three URL's, the first two being excel '.png' files and the third being a link to a wordpress site that looks to prompt you for a username and password. Phishing! Lets open the website up to confirm.

<img src="/img/Phishing.png">

Yep, it's a standard looking phishing site disguised as a.. Microsoft Excel login page? I can't remember ever seeing a legitimate one of those in my 15+ years of using Excel. Interesting. We already know that no one in the organization has had the '.htm' on their machines, but it's still possible that this website was reached and not reported to our sensors, so lets check out the firewall logs for hits on this new phishing site. No hits besides ours? Excellent! Now back to poking around the site. If we go up a few directories we reach the parent directory and can confirm that this site is being used for other phishing campaigns such as Office 365 and LinkedIn phishing.

<img src="/img/O365.png">

Drilling back to the main site itself we can explore around until we find contact information for the legitimate site owner and send them an email letting them know their site has been compromised and advise them to seek remediation. Granted that this site might have been setup by the attackers themselves in the first place, though that is unlikely. This is something that I like to do, as even a small effort like this could help to clean up attacker infrastructure.
