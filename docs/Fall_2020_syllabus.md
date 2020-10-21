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

<br />
<br />

## Week 2: Background on network-stats
Oct 12 - 16
1. Clone [network-stats](https://github.com/viasat/network-stats) repo
2. Create 5 minute chunks of network-stats data and upload to Google Drive with correct nomenclature
3. Begin exploring the data (with your favorite tools... Tableau, Jupyter notebook, etc)

### Week 2 Participation Homework:
Zip and upload your network-stats CSV captures to the Google Drive (link in Slack - do not share or post publicly).

The CSV and Zip filenames must follow this convention:  
`<username>-<streaming provider>[-<quality>]-<playback speed>-<vpn/novpn>-<platform>-<clean/noisy>-<date>.<csv/zip>`

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
* `quality` = **OPTIONAL - OMIT IF NOT APPLICABLE** Some video providers such as YouTube and Vimeo let you choose the playback quality.  If you choose a specific video resolution quality, identify it here.  Use the same value you see in the provider's quality menu.  Examples:
  * **YouTube** - 144p, 240p, 480p, 720p60, 1080p60, 1440p60, 2160p60
  * **Vimeo** - 360p, 540p, 720p, 1080p, 2K, 4K
  * If you find others, let us know in the Slack and we'll update this document!
* `playback speed` = Playback speed, examples: 0.25x, 1x, 1.5x, 2x
* `vpn/novpn` = identify whether you are using a VPN tunnel or not
* `platform` = mac, windows, linux
* `clean/noisy` = Are you performing other internet activities while streaming?  "Clean" means you are only streaming video.  "Noisy" means you are doing other online activities while streaming, thus adding additional network traffic.
* `date` - date you started the packet capture in yyyymmdd format

**<mark>NEW!</mark>**  If you collect multiple captures on the dame day (i.e., all the labels in the filename match), append an incrementing lower-case letter suffix to the filename.  E.g., `...20201021a.csv`, `...20201021b.csv`, `...20201021c.csv`, etc.


#### **Video Streaming Criteria**
* Nothing live (youtube live, twitch)
* Long form (> 5 mins videos) only.  No TikTok, Instagram, etc
* No mobile devices (phones, tablets)
* No 360° / VR videos **<mark>NEW!</mark>**

<br />
<br />


## Week 3: Analyze network-stats data
Oct 19 - 23
1. Capture network-stats data for YouTube at different resolution settings.
2. Continue exploring the data from last week and compare to what is observed with YouTube at different resolution settings.


### Week 3 Participation Homework:   **<mark>NEW!</mark>**
Capture multiple YouTube videos at different resolutions.  See the update to the CSV file naming convention above to capture the video quality in the filename.

Using your visualization tool of choice (Jupyter/Python/Pandas, Tableau, etc) perform some exploratory data analysis of your new captures.
* Compare the results to each other.  Create a slide presentation of a few slides with annotated screenshots.  We'd like to see your observations for how the network stats captures compare for YouTube at different resolutions.
* Also explore some of your captures from last week.  Add a few slides with your screenshots and annotations.

We are starting to do some preliminary feature engineering.  Through our observations, we are identifying candidate features we could use in our machine learning models.  We will explore this in greater detail in Weeks 4 (no VPN) and 5 (with VPN).

***Tips for packet captures***
* Run network-stats in extended output CSV mode (`-e <filename>`)
* Start network-stats *before* starting to play the video. 

<br />
<br />


## Week 4: What is the typical pattern of video streaming WITHOUT vpn?
Oct 26 - 30  
1. Look for patterns that suggest streaming is occuring (vs web browsing, etc) ***WITHOUT VPN***
2. Feature engineer the pattern(s)
3. Implement a machine learning algorithm to classify the occurrence of streaming

<br />
<br />

## Week 5: What is the typical pattern of video streaming WITH vpn?
Nov 2 - 6

Same as week 4 but ***WITH VPN***

<br />
<br />

## Week 6: Increase complexity of streaming conditions
Nov 9 - 13
1. Iterate steps to look at differences in:
  * provider
  * platform
  * clean vs noisy

<br />
<br />

## Week 7: Continue efforts from week 6
Nov 16 - 20

<br />
<br />

## Week 8: Thanksgiving Break
Nov 23 - 27

<br />
<br />

## Week 9
Nov 30 - Dec 4
1. Present plan for next quarter
2. Consider network-stats extended outputs

<br />
<br />

## Week 10
Dec 7 - 11
1. Present results to Viasat
