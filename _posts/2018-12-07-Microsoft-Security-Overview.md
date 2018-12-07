---
layout: post
title: Microsoft O365 Security and Compliance Center
subtitle: Overview - The first of many
tags: [Blue Team, O365]
image: "/img/SecurityCompliance/SecurityComplianceOverview.png"
share-img: "/img/SecurityCompliance/SecurityComplianceOverview.png"
comments: true
---

Over the next few blog posts I will be exploring some of the capabilities and features on the long list of security products that Microsoft offers. First on the list is the overview of the Security and Compliance center in Office 365, the next post will focus on exploring the alerting capabilities, and writing a few specific ones that have come in clutch for me. This portal comes standard baseline Office 365, and to my knowledge does not require any additional licensing. That being said, it is also the ugly step-child version of Microsoft's Cloud App Security Center, which is available with their Enterprise Mobility Suite (EMS) + E5 license, which comes with additional "advanced" alerting capabilities and has a more SIEM-type feel to it.

The Security and Compliance center by comparison has a more "legacy" feel to it, but still has a good amount of capabilities, though some are less straight forward than their Cloud App Security counterparts. The portal has multiple subsections, as found below.

<img src="/img/SecurityCompliance/HomeScreen.png">

### Home: 
Gives you a customizable tile dashboard.

### Alerts: 
Gives you… well.. Alerts? You can view them individually, set up alerting dashboards, and configure alerting policies. This is also where you integrate the Cloud App Security Center, under the "Managed Advanced Alerts".

### Permissions: 
Here you can assign permissions to people in your organization so they can perform tasks in the Security & Compliance Center.

### Classifications: 
This relates to the data classifications you set to classify email messages, documents, sites, and everything 'Office' related. This can automatically push out labels (based on your settings) which can control access and even encrypt.

### Data Loss Prevention: 
The companion to the Classifications tab, here you can create policies based on the classifications that were setup previously, and track your policy matches over time. Here is where you will also find the second tie in to Cloud App Security, under "App Permissions". 

### Data Governance: 
This is the section for importing your PST files, setting retention dates on email archives and Skype logs, creating events and other vaguely security related items. This section is heavy on the compliance side, and isn't a sandbox that I've spent much time in.

### Threat Management: 
This section contains the bulk of the functionality within the Security and Compliance Center. Here you can view your malware trends and phishing campaigns, review users who were targeted with phishing emails, and check out what O365 detects as spoofed domains that have been seen in your environment. This is also where you hunt through your inbound/outbound email when you need to perform some Incident Response. You can track what has been identified as an incident, see what emails are in quarantine, and unblock users who were sanctioned for sending out too many spam-like emails. You also configure all of your email policies here, such as enabling safe links, and your spam settings. 

There's also a new feature out in preview; Attack Simulator! When this first released I turned up my nose at this, as when I run internal pen-tests I prefer to use my own set of tools that have far greater functionality and capability. But after I got down off my high horse I realized that this feature greatly lowered the bar to entry for taking a proactive security stance for the average company. This feature allows you to manage and send out spear phishing campaigns, do brute force password attacks against your users, and conduct password sprays in your O365 environment, looking for that easy low hanging fruit.

<img src="/img/SecurityCompliance/AttackSim.png">

### Mail Flow: 
Everything email related, there's a dashboard and you can conduct message traces here.

### Data Privacy: 
Here's where you'll find your GDPR dashboard, create Data Subject Requests, and generally view items related to, well, data privacy.
Search and Investigation: Here admins can perform content searches on users mailboxes. Super useful when you have an internal email compromise and need to see what kind of damage the compromised account could be bringing. You can also search the audit logs on user accounts looking to see if a user deleted a document, and you can kick off the eDiscovery process for your legal department. 

### Reports: 
Create reports on your environment, schedule and download them. Not a very interesting section, but a useful one.

Next time we will delve into the alerting structure that comes stock with the product, and explore creating custom alerts.
