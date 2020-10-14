---
layout: default
title: VPN X-Ray Fall 2020 Syllabus
description:  Week by week summary of assignments and goals
---

[(back to home)](./)

## Week 1: Project overview and course expectations
Oct 5 - 9
1. Complete reading outlined in the course overview (General networking, video streaming, vpn, networking architecture)
2. Install [Wireshark](https://www.wireshark.org/)
3. Capture some packets

### Week 1 Participation Homework:
Annotate a few screenshots of your Wireshark packet captures with your observations and understanding about what they show.  We suggest creating a presentation in PowerPoint or similar where you can paste your screenshots and overlay your annotations in text boxes with arrows pointing to the relevant part of the capture.


## Week 2: Background on network-stats
Oct 12 - 16
1. Clone [network-stats](https://github.com/viasat/network-stats) repo
2. Create 5 minute chunks of network-stats data and upload to Google Drive with correct nomenclature
3. Begin exploring the data (with your favorite tools... Tableau, Jupyter notebook, etc)

### Week 2 Participation Homework:  **<mark>NEW!</mark>**
Zip and upload your network-stats CSV captures to the Google Drive (link in Slack - do not share or post publicly).

The CSV and Zip filenames must follow this convention:  
`<username>-<streaming provider>-<vpn/novpn>-<platform>-<clean/noisy>-<date>.<csv/zip>`

* `username` = your UCSD username
* `streaming provider` = name of streaming provider. If applicable, use from this list:
  * amazonprime
  * disneyplus
  * espnplus
  * hbomax
  * hulu
  * netflix
  * vimeo
  * youtube

*If your streaming provider is not in this list, that's fine - identify it and we can add it to this list.*
* `vpn/novpn` = identify whether you are using a VPN tunnel or not
* `platform` = mac, windows, linux
* `clean/noisy` = Are you performing other internet activities while streaming?  "Clean" means you are only streaming video.  "Noisy" means you are doing other online activities while streaming, thus adding additional network traffic.
* `date` - date you started the packet capture in yyyymmdd format

#### **Video Streaming Criteria**
* Nothing live (youtube live, twitch)
* Long form (> 5 mins videos) only.  No TikTok, Instagram, etc
* No mobile devices (phones, tablets)

   
     



## Week 3: Analyze network-stats data
Oct 19 - 23
1. Capture network-stats data for YouTube at different resolution settings
2. Continue exploring the data from last week and compare to what is observed with YouTube at different resolution settings

## Week 4: What is the typical pattern of video streaming WITHOUT vpn?
Oct 26 - 30
1. Look for patterns that suggest streaming is occuring (vs web browsing, etc) ***WITHOUT VPN***
2. Feature engineer the pattern(s)
3. Implement a machine learning algorithm to classify the occurrence of streaming

## Week 5: What is the typical pattern of video streaming WITH vpn?
Nov 2 - 6
Same as week 4 but ***WITH VPN***

## Week 6: Increase complexity of streaming conditions
Nov 9 - 13
1. Iterate steps to look at differences in:
  * provider
  * platform
  * clean vs noisy

## Week 7: Continue efforts from week 6
Nov 16 - 20

## Week 8: Thanksgiving Break
Nov 23 - 27

## Week 9
Nov 30 - Dec 4
1. Present plan for next quarter
2. Consider network-stats extended outputs

## Week 10
Dec 7 - 11
1. Present results to Viasat
