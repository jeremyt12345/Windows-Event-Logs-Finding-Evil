# Windows-Event-Logs-Finding-Evil
Windows Security Log investigation (HTB CDSA lab). Analyzed Event ID 4624, pivoted using the Logon ID, and correlated activity via XML filtering to identify the executable that modified audit settings (Event ID 4907). Strengthened session-based correlation and relational SOC analysis skills through timeline investigation.


## Overview
This lab focused on investigating Windows Security Event Logs to identify which executable modified auditing settings. The investigation began with Event ID 4624 and required pivoting through session correlation to uncover the responsible process.

---

## Investigation Steps

1. Filtered Security logs for **Event ID 4624**
2. Identified Logon ID `0x3e7`
3. Used XML filtering to correlate events tied to that Logon ID
4. Discovered Event ID 4907 (Audit Policy Change)
5. Identified the executable responsible for modifying auditing settings

---

## Key Finding

The executable responsible for modifying auditing settings was:

---

## Screenshots

### 1. Filtering Event ID 4624
![4624 Filter](screenshots/01_filter_4624.png)

### 2. XML Filter Pivot Using Logon ID
![XML Filter](screenshots/02_xml_filter.png)

### 3. Event ID 4907 Showing Executable
![4907 Event](screenshots/03_event_4907.png)

---

## Reflection

This lab wasn’t technically difficult, but it challenged my investigative thinking.

Initially, my approach was very linear — I focused only on Event ID 4624 and expected the answer to be directly visible there. When it wasn’t, I stalled.  

The turning point was understanding that strong SOC analysis isn’t about single-event inspection — it’s about correlation.

Pivoting using the Logon ID and building a timeline helped me see how events relate to each other within the same session.

This exercise strengthened my ability to:
- Think relationally instead of linearly
- Correlate session-based activity
- Use XML queries for focused log analysis
- Perform timeline-driven investigations

Still improving my correlation mindset, but this lab was a solid step forward.
