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
translationKey: "mvt-mesh"
---

## What is WARD?

WARD is a modular, open-source, decentralised, distributed, offline, and privacy-respecting tool for behavioral mobile forensics and acquisition using Android ADB–accessible data. It's developed in house by our team. 

It grabs and analyses a wide range of live-state system artifacts — crash logs, process and thread listings, diagnostic outputs, Wi-Fi manager logs, installed apps — to preserve forensic evidence and surface patterns that might indicate spyware or other unwanted activity.

Instead of relying on vendor telemetry, malware signatures, or preloaded IOCs, WARD uses heuristics to spot anomalies like:

    abnormal wakelock usage
    unexplained battery drain
    location misuse
    persistent background processes
    memory crashes
    exploitation

This lets civil society, journalists, and investigators run self-service device triage — making spyware identification more readily available to the many.

We will be releasing this, open-source, at the end of 2025.
