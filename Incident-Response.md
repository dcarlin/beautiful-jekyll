---
layout: page
title: Incident Response
---

This page contains a list of the open source / free Incident Response tools that I've used in the past and can be compiled for use for those just starting out. Most of these tools I still use today, although there are a lot of paid / proprietary tools that I now also have access to that are not mentioned here. Most of the Incident Response that I do is focused on Malware Eradication and Recovery, I've only had to conduct forensics with the intent of legal proceedings once. So keep that in mind when you review this list for your own use.

### Virtual Machines
Below are the VM's that I have setup on my laptop at any given time, to be used for Incident Response, Pen Testing, or doing CTF's. The sub notes are the software that I configure them with.

- **Win 7 or Win 10**
		○ Malware Analysis Tools
- **Ubuntu**
	- CRITs
		-  Malware Analysis Platform
	- The Hive 
		- Analyst / TTP Casebook
	- Cuckoo Sandbox
		- Malware Analysis Sandbox
	- Google Rapid Response (GRR)
		- Clients deployed to machines, server running interrogation.
	- Network Traffic Analysis Tools
- **Security Onion**
	- Intrusion Detection System bundle that includes Snort, Bro, and Suricata.
- **Kali Linux**
	- Loaded with the tools in my Install Script (github)
	- Spyder - Python Scripting (optional)

### Forensics Tools
- Google Rapid Response (Agent/Server)
	- Incident response framework focused on remote live forensics
- CimSweep
	- Remotely obtain the following from all versions of windows; requires Admin creds. (PowerShell).
	- Registry keys, values, value types, and value content with optional recursion 
	- Directory and file listing with optional recursion, Event log entries, Services, Processes
- FTK Imager
	- Hard drive and memory imaging tool
- Reg Ripper
	- Exports the contents of the registry
- Autopsy / Sleuth Kit
	- Memory forensics / timelining tool.
- Mandiant Redline
	- IOC Extractor
	
### Malware Discovery and Removal Tools
- Malwarebytes
	- Anti Virus Tool
- Malwarebytes Anti RootKit
	- Rootkit discovery
- Adware Cleaner
	- Adware Cleaner
- Super Anti Spyware
	- Spyware / Adware Cleaner
- Spybot
	- Spyware cleaner
- Crowd Inspect
	- Process Inspection Tool (Virus Total tie in)
- Hijack This - Portable
	- Searches for evidence of web hijacking

### USB Drive's
- Bootable Linux Distro 
	- Kali, Ubuntu or SIFT
- Break Glass IR USB
	- AV Tools
	- Forensics Tools
	- Malware Analysis Tools
	- Sys Internals Suite
	
