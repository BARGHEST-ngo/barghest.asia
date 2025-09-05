---
title: "_WARD for Android"
date: 2024-03-27
description: "Introducing WARD for Android, a heuristic forensics engine for self-service forensics analysis & acquisition."
draft: false
author: "Umbra"
type: "post"
coffee: 1
tags: ["security", "forensics", "mobile", "MVT", "WARD",  "spyware", "civil-society"]
categories: ["research", "forensics-tools", "publications"]
cover: "https://www.0x0v1.com/content/images/size/w1000/2025/03/ChatGPT-Image-Mar-27--2025--02_47_49-PM.png"
alt: ""
translationKey: "mesh"
---

## What is WARD?

WARD is a modular, open-source, decentralised, distributed, offline, and privacy-respecting tool for behavioral mobile forensics and acquisition using Android ADB–accessible data. It's developed in house by our team. ://WARD 

WARD is a modular, open-source, decentralised tool for **behavioural mobile forensics** and artifact acquisition using Android ADB–accessible data. It’s developed by **[BARGHEST](https://barghest.asia)**, a non-profit supporting the democratisation of threat intelligence in the majority world.
Heavily inspired by the legendary work that is [AndroidQF](https://github.com/botherder/androidqf) we wanted to take this further by enhancing coverage to forensics logs and building a heurstics behavioural pattern engine ontop for self-service forensics analysis providing a programmatic triaging mechanism. WARD collects and analyses a wide range of live-state system artifacts — crash logs, process/thread listings, diagnostic outputs, Wi-Fi manager logs, installed apps — to preserve forensic evidence and surface patterns that might indicate spyware or other unwanted activity.

This enables civil society, journalists, and investigators to run **self-service device triage**, making spyware identification more accessible to many.

Rather than vendor telemetry, malware signatures, or preloaded IOCs, WARD uses behavioral based heuristics to spot patterns of malicious behavior. Our current heurstics cover:

- *Memory analysis:* Signals against suspicious in-memory DEX loading, secondary DEX files from external storage, and shell-initiated code compilation that may indicate fileless malware or dynamic code injection.
- *System security:* Signals against persistence mechanisms, suspicious app behaviors, unusual service patterns, and malware-like activity patterns across system logs
- *Permission analysis:* Identifies dangerous permission abuse, privilege escalation attempts, and apps requesting excessive or suspicious permission combinations
- *Crash analysis:* Detects crash patterns that may indicate exploitation attempts, buffer/heap overflows, or targeted attacks against system components
- *Memory exploitation:* Attempts to identifies memory exploitation attempts synonymous with zero-click and one-click activity. It performs episode-based temporal analysis to identify memory corruption and exploitation attempts. Monitoring native crashes (SIGSEGV, SIGABRT, SIGBUS), heap exploitation (overflows, UAF, double-free), kernel driver abuse (Binder, GPU, futex, perf events), and high-value zero-click targets like media parsers, WebView, and system services. Related events are grouped within 15-second windows, applying scoring boosts for background zero-click exploits and dampening for user-triggered one-click crashes, while detecting repeated exploitation attempts and post-exploitation artifacts like HPROF dumps, OOM states, and log tampering.
- *User analysis:* Detects anomalous user interaction patterns and suspicious user behavior that may indicate compromise
- *System anomalies (disabled by default):* Catches general system irregularities and anomalous behaviors that don't fit other specific categories
- *Process anomalies (disabbled by default):* Monitors process creation patterns, suspicious process behaviors, and process-level indicators of compromise

://Data_collection: The engine collects both Bug Report and all forensic ADB logs excluding PII data (such as SMS). It stores these in the collections folder for evidence & merges the two, and parses it all for analysis. 

---

## ://UPDATES
### [WARD Core v2.0.0-beta — Standalone Engine](https://github.com/BARGHEST-ngo/_WARD-core)

We have now released WARD Core v2.0.0-beta
This engine is designed specifically for the WARD app and thus, functionality exists purely on the basis of that right now. Usability isn't really the focus of this part of the project, since it's built specifically to intergrate into our UI components. The use of the core engine may be difficult for non-technical and heurstic results may be difficult to interpret when using the core engine if you're not familar with what you're looking at. This is because it's designed to be technical under the hood. If you are a non-technical user and wish to abstract away the technical aspects, you should usee the app first. For technical users, we will release development guides in the coming months.

This is the standalone beta release of the WARD core engine — the backend engine of the main WARD software. The primary desktop application lives here: BARGHEST-ngo/_WARD-UI.

- **WARD Core as a package:** now a Python package (`ward-core`) that can be installed and used independently.  
- **Self-contained binaries:** pre-built executables for Windows, macOS, and Linux (no Python required).  
- **Preserved CLI:** existing command-line functionality maintained for backward compatibility.  
- **Enhanced metadata:** analysis results include engine and schema versions for better integration.

---
