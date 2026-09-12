# Week 2: Suspicious File on a Nurse's Workstation
**Course:** CPSC 4584 | Special Topics in Information Security
**Date:** September 7, 2026
**Analyst:** Jesus Reyes
**Incident ID:** INC-2026-0907-001

---

## Incident Summary

The Maplewood SOC detected an unexpected file "patient_notes.txt". This file was inside a nurses account and was created overnight on off duty hours. 

---

## Key Findings

**Permission Finding:** The permissions of that file was -rwxr--r-- whic is a regular file. The execute permission though is highly unusual for a .txt file.
**File Type Finding:** The file type after file command shows that it is indeed an ASCII text that has an executable script. 
**Timestamp Finding:** The timestamp of the file showed very important information about the file such as the access, modification, and change times.
**Strings Finding:** The string findings shows any hidden readable text that allowed for further investigating. 

---

## Terminal Commands Used

| Command | Purpose |
|---------|---------|
| pwd && ls -la | This command helped verify which directory I was on along with any files in it. 
| file [filename] | This command verified the file based on the included content. 
| stat [filename] | The stat command gave me a detailed list of the metadata, permissions, inode, and timestamps of the file. 
| strings [filename] | The strings command allowed me to extract any readable information that could help with the investigation.
| find . -mtime -1 -type f | This command allowed me to find any files that were modified within the 1 day timeframe narrowing down my search. 

---

## Escalation Recommendation

I would without a doubt after the findings escalate the incident to a tier 2 analyst. The strongest evidence was that the file appeared to be created at a time in which the clinic is closed along with the executable permission for that supposed .txt file. The tier 2 analyst should do further investigation by examining system logs and how this file was created and by who.   

---
*CPSC 4584 | Governors State University | Fall 2026*
    
