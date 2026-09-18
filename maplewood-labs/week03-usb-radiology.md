# Week 3: Unauthorized USB Drive in Radiology
**Course:** CPSC 4584 | Special Topics in Information Security
**Date:** September 14, 2026
**Analyst:** [Your Name]
**Incident ID:** INC-2026-0914-001

---

## Incident Summary

[An unauthorized and unmarked USB drive was found connected to a restricted Radiology workstation. The USB was removed and used as evidence.]

---

## Chain of Custody

[Every transfer of the USB drive must be documented to protect the integrity of the information in the USB drive. Documenting allows the analyst to backtrack where, when, and who handled the USB drive. This is highly important when investigating.]

---

## Key Encoding Finding

**String Found:** Y3VybCAtcyAtbyAvZGV2L251bGw=
**Encoding Type:** [Base64]
**Decoded Content:** [curl -s -o /dev/null]
**Significance:** [This finding allows an analyst to know what the string targets and in what way.]

---

## Terminal Commands Used

| Command | Purpose |
|---------|---------|
| echo "..." \| base64 | [Base 64 gives an insight on how readable text can be represented as a string of letters, numbers, and characters.] |
| echo "..." \| base64 -d | [The decoding of the string revealed a command fragment "curl -s -o /dev/null".] |
| xxd .bashrc \| head -6 | [The hex output showed the first 6 lines of the .bashrc file as hexadecimal bytes and any readable text that was included with the output.] |
| strings .bashrc \| grep -i "..." | [Filtering helped extract any readable strings and aliases which narrowed the search.] |

---

## Escalation Recommendation

[I would escalate the incident to Tier 2 for further investigation. The strongest evidence is that the usb was unauthorized and connected to a restricted workstation. The string that decoded to the command fragment can also be used as strong evidence. The unanswered questions include who connected the usb drive and was the file in the usb drive executed.  ]

---
*CPSC 4584 | Governors State University | Fall 2026*
    
