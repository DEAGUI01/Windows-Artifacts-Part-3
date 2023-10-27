<h1>Forensic Image Conversion and Analysis</h1>


<h2>Description</h2>
In this investigative project, a comprehensive forensic analysis was conducted on a Windows 10 Pro environment to inspect various system artifacts. Utilizing a suite of specialized tools including $I_Parse, Evtx Explorer, Notepad, Timeline Explorer, and PECmd, each phase of the project revealed critical insights into user and system activities over a period of time. It includes the following tasks:
<br />
<br />
- <b>Analysis of $Recycle.Bin Files</b> 
<br />
- <b>Scheduled Tasks Analysis</b>
<br />
- <b>Event Logs Parsing and Analysis</b>
<br />
- <b>Prefetch Files Analysis</b>
<br />


<h2>Software and Utilities Used</h2>
- <b>$I_Parse</b>
<br />
- <b>Evtx Explorer</b>
<br />
- <b>Notepad</b>
<br />
- <b>Timeline Explorer</b>
<br />
- <b>PECmd</b>

<h2>Environments Used </h2>
- <b>Windows 10 Pro</b>


<h2>Project Walkthrough</h2>
<h3>Parse and Analyze $Recycle.Bin Files</h3>
<p align="center">

Parse the Recycle Bin $I files in the “Recycle Bin” folder using $I_Parse <br/>
<img src="https://i.imgur.com/p9JdB6X.png" height="80%" width="80%" alt="Log into Windows"/>
<br />
<br />
Answer the following questions: 
<br />
<br />
1) How many different files were sent to this Recycle Bin, based on the available $I files?
<br />
<br />
6 Files
<br />
<br />
2) What is the version of operating system from which these files were removed? 
<br />
<br />
Windows 10
<br />
<br />
3) What date and time was “Luna Owl.jpg” sent to the Recycle Bin? 
<br />
<br />
01/27/2017 17:35:49 UTC
<br />
<br />
4) What was the full path to “Pygmy Owl.jpg” before it was sent to the Recycle Bin?
<br />
<br />
C:\Users\Sarah M\Desktop\pets\Pygmy Owl.jpg
<br />
<br />
5) What is the name of the file that was sent to the Recycle Bin most recently?
<br />
<br />
Next pet.jpg
<br />
<br />
6) What is the file size in bytes of the largest file in this Recycle Bin?
<br />
<br />
593265 bytes
<br />
<br />

<h3>Analyze Scheduled Tasks</h3>

Analyze the scheduled tasks in the “Scheduled Tasks” folder:
 <br/>
<img src="https://i.imgur.com/XRfmAfC.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Answer the following questions:
<br />
<br />
1) How often is GoogleUpdateTaskMachineCore scheduled to execute?
<img src="https://i.imgur.com/wybwMRL.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Daily
<br />
<br />
2) When is the “dkfo4f” scheduled task configured to execute? 
<img src="https://i.imgur.com/ERak5v4.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Every time the user with the user id: IN-LPUE2OJ805Q\Win7 logs into the system
<br />
<br />
3) When was the “dkfo4f” scheduled task created?
<img src="https://i.imgur.com/C5azmg3.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Date: 2013-06-20T11:28:50.5032431
<br />
<br />
4) What account created the “dkf04f” schedule task?
<img src="https://i.imgur.com/GpPhEp1.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Author: WIN-LPUE2OJ805Q\Guest
<br />
<br />
5) What is the full path to the .exe that will launch when the “dff04f” scheduled task is
triggered? 
<img src="https://i.imgur.com/Usb99fM.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
C:\Users\Win7\AppData\Local\Temp\dkfo4f.exe
<br />
<br />

<h3>Parse and Analyze Event Logs</h3>
Parse the event logs in the “Event Logs” folder using Evtx Explorer (evtxcmd). Be sure to issue
the sync command after downloading Evtx Explorer to download the latest maps (“evtxcmd.exe
–sync”). Analyze the output of Evtx Explorer using Timeline Explorer <br/>
<img src="https://i.imgur.com/qQBOe5d.png" height="80%" width="80%" alt="log into Kali Linux"/>
<br />
<br />
Answer the following questions:
<br />
<br />
1) When was the most recent event record created?
<img src="https://i.imgur.com/b2fJX8f.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Time Created
2020-09-19 04:52:11
<br />
<br />
2) How many Windows RDP logons are present in the event logs? To identify RDP logons,
filter for Event ID 4624, Type 10 (i.e. “LogonType 10” in Payload Data2 column). 
<img src="https://i.imgur.com/PheZX1z.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
4
<br />
<br />
3) Group the Evtx Explorer output by “Map Description” in Timeline Explorer. Based on the
map description, how many times was a computer account changed?
<img src="https://i.imgur.com/Tm1OQnC.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
15
<br />
<br />
4) Group the Evtx Explorer output by “Map Description” in Timeline Explorer. What is the
name of the account that was deleted on 2020-09-18 01:05:16?
<img src="https://i.imgur.com/s0tlsN2.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
mortysmith
<br />
<br />
5) Group the Evtx Explorer output by “Map Description” in Timeline Explorer. What is the
name of the application that encountered an error on 2020-09-19?
<img src="https://i.imgur.com/maaC6EV.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
spoolsv.exe
<br />
<br />
6) Group the Evtx Explorer output by “Map Description” in Timeline Explorer. When is the
last time the OS was shutdown?
<img src="https://i.imgur.com/Udc5ejw.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Time Created
2020-09-18 23:10:53
<br />
<br />
7) Group the Evtx Explorer output by “Map Description” in Timeline Explorer. How many
outgoing RDP connections are present in the event logs?
<img src="https://i.imgur.com/9uiJczf.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
1
<br />
<br />
8) Group the Evtx Explorer output by “Map Description” in Timeline Explorer. What is the
target account associated with the most recent failed logon?
<img src="https://i.imgur.com/p3Pdyoh.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Target: \Administrator
<br />
<br />
9) Group the Evtx Explorer output by “Map Description” in Timeline Explorer. What is the
IP address of the remote host from which the RDP network connections were established
on 2020-09-19?
<img src="https://i.imgur.com/jlRISCc.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Remote Host
194.61.24.102
<br />
<br />
10) Based on analysis of the event logs, on what day was VMWare Tools installed on the
system?
<img src="https://i.imgur.com/cDQfHEI.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Time Created
2020-09-17 17:03:03
<br />
<br />
11) Group the Evtx Explorer output by “Map Description” in Timeline Explorer. What is the
earliest creation date of the scheduled task called “\Microsoft\Windows\TPM\TpmMaintenance”?
<img src="https://i.imgur.com/4ATRpB3.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Time Created
2020-09-17 17:57:18
<br />
<br />
12) What is the Security Identifier (SID) of the account that was logged in when the service
“mszhao” was installed?
<img src="https://i.imgur.com/ISoDgOr.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
User Id
S-1-5-21-2232410529-1445159330-2725690660-500
<br />
<br />
13) On what day was the account “summersmith” created?7
<img src="https://i.imgur.com/PZY67km.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Time Created
2020-09-18 00:53:25
<br />
<br />
14) Based on analysis of the event logs, how many user accounts were created on this
system and NOT deleted at a later date?
<img src="https://i.imgur.com/3SbBBJY.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
5
<br />
<br />
15) Based on analysis of the event logs, what is the name of the account associated with the
security identifier (SID) “S-1-5-21-2232410529-1445159330-2725690660-502”?
<img src="https://i.imgur.com/J1zbS5U.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
krbtgt
<br />
<br />
16) Based on analysis of the event logs, what is the command that was executed 11 seconds
after the first remote desktop services session logon on 2020-09-19? HINT: If two event
records display the same created timestamp in Timeline Explorer, report the first of the
two records (i.e. the record with the lowest “line number” value) for your answer.
<img src="https://i.imgur.com/FzldBFR.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
"C:\Windows\system32\vm3dservice.exe" -u
<br />
<br />

<h3>Parse and Analyze Prefetch Files</h3>
Parse the Prefetch files in the “Prefetch” folder using PECmd <br/>
<img src="https://i.imgur.com/YTpsnRZ.png" height="80%" width="80%" alt="log into Kali Linux"/>
<br />
<br />
Answer the following questions:
<br />
<br />
1) Based on analysis of the Prefetch files, what is the name of the program executed most
recently?
<img src="https://i.imgur.com/sBsarPY.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
SVCHOST.EXE
<br />
<br />
2) Based on analysis of the Prefetch files, how many different program executions occurred
on January 28, 2017?
<img src="https://i.imgur.com/s761VgT.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
65
<br />
<br />
3) Based on analysis of the Prefetch files, what is the most recent execution time of
“\VOLUME{01d2783140af8e9f-14412537}\WINDOWS\SYSWOW64\CMD.EXE”? 
<img src="https://i.imgur.com/WdEcAlM.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
2017-02-02 22:25:37
<br />
<br />
4) Based on analysis of the Prefetch files, how many times was WMIC.exe executed?
<img src="https://i.imgur.com/xAIXVqU.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
10 Times
<br />
<br />
5) What is the volume serial number of the volume from which WMIC.exe was executed?
<img src="https://i.imgur.com/ugfHHyk.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
14412537
<br />
<br />
6) Based on analysis of the Prefetch files, what is the number of locations from which
CMD.exe has been executed?
<img src="https://i.imgur.com/bEd1Q2J.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
3 different locations
<br />
<br />
7) What is the operating system version associated with the parsed Prefetch files?
<img src="https://i.imgur.com/4A2xKPC.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
Windows 10 or Windows 11
<br />
<br />
8) Based on analysis of the Prefetch files, what is the name of the program that has been
executed 62 times from a single location?

<img src="https://i.imgur.com/c8d9sBc.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
CHROME.EXE
<br />
<br />
9) Based on analysis of the Prefetch files, what is the second-most recent execution time of
“IASTORICON.EXE”?

<img src="https://i.imgur.com/DIoNYtb.png" height="80%" width="80%" alt="dir /r"/>
<br />
<br />
2017-02-01 19:08:54
<br />
<br />

<h2>Conclusion </h2>
The extensive forensic examination of the Windows 10 Pro environment elucidates a significant amount of intricate details concerning both user and system activities over a specific duration. Through the adept utilization of specialized forensic tools, this project exemplifies a methodical approach towards dissecting and analyzing digital artifacts, which is imperative in modern investigative or cybersecurity endeavors.
<br />
<br />
Rich Data Retrieval:
<br />
The project demonstrates the ability to retrieve rich data from various system artifacts, showcasing how digital remnants can provide a detailed narrative of user interactions and system events. The meticulous examination of $Recycle.Bin, Scheduled Tasks, Event Logs, and Prefetch files offers a panoramic view of the system's operational landscape over time.
<br />
<br />
Technical Proficiency:
<br />
The adept use of forensic tools like $I_Parse, Evtx Explorer, Timeline Explorer, and PECmd underscores the technical proficiency required to navigate and interpret complex digital landscapes. These tools enabled precise analysis and interpretation of digital artifacts, presenting a structured methodology to extract actionable insights.
<br />
<br />
Security and Investigative Implications:
<br />
The findings from this project underscore the critical role forensic analysis plays in cybersecurity and investigative fields. By unearthing details like RDP logons, scheduled task configurations, and program executions, the project provides a foundation for identifying anomalous behaviors or potential security threats.
Future Scalability:
<br />
The structured approach showcased in this project lays down a scalable framework that can be adapted for larger or more complex forensic investigations. This scalability is vital in continuously evolving digital domains, ensuring that investigative methodologies remain robust against advancing challenges.
<br />
<br />
Knowledge Advancement:
<br />
Engaging in such detailed forensic analysis not only advances individual and organizational knowledge but also contributes to the broader community by sharing methodologies and findings. This project serves as a valuable reference, illustrating a thorough and methodical approach towards understanding and analyzing digital environments.
