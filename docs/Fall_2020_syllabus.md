---
layout: default
title: VPN X-Ray Fall 2020 Syllabus
description:  Week by week summary of assignments and goals
---

### [Home](./)

<br />

## Jump to [Current week!](#week-7-binary-classifiers)

<br />
<br />

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

#### **No Video Streaming**  
`<username>-novideo-<vpn/novpn>-<platform>-<date>.<csv/zip>`


#### **Video Streaming**  
`<username>-<streaming provider>[-<quality>]-<playback speed>-<vpn/novpn>-<platform>-<clean/noisy>-<date>.<csv/zip>`

*Label Definitions*  
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

If you collect multiple captures on the dame day (i.e., all the labels in the filename match), append an incrementing lower-case letter suffix to the filename.  E.g., `...20201021a.csv`, `...20201021b.csv`, `...20201021c.csv`, etc.


#### **Video Streaming Criteria**
* Nothing live (youtube live, twitch)
* Long form (> 5 mins videos) only.  No TikTok, Instagram, etc
* No mobile devices (phones, tablets)
* No 360° / VR videos

<br />
<br />


## Week 3: Analyze network-stats data
Oct 19 - 23
1. Capture network-stats data for YouTube at different resolution settings.
2. Continue exploring the data from last week and compare to what is observed with YouTube at different resolution settings.


### Week 3 Participation Homework:
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


## Week 4: Exploring the negative use case
Oct 26 - 30  
1. Review and discuss analysis of streaming scenarios captured so far (VPN, no VPN, different providers, different video qualities, noisy vs. "clean")
2. Discuss the negative use case - no video streaming (VPN and no VPN)

### Week 4 Participation Homework
1. Pull the latest version of network-stats from the git repo (https://github.viasat.com/Viasat/network-stats) and verify that it's working for you.
    * Report any weirdness in the Slack channel!
2. Capture a total of **30 minutes** of general internet activity (no video streaming) without VPN.
3. Capture a total of **30 minutes** of video streaming with VPN.
4. EDA your captures, and create a slide presentation with 2-3 visualizations for general internet activity, and 2-3 visualizations for streaming.  Annotate your charts with your observations.
   * **Focus on the extended part of the output for this week's analysis.**
5. Upload your assignments to Canvas.
6. Zip all your CSV files and upload to the new "Good Data" subfolder in Google Drive.

**NOTE:**  30 minutes of data should be split into 6 CSV files each containing 5 minutes of capture data.

***Tips for packet captures***
* Run network-stats in extended output CSV mode (`-e <filename>`)
* Start network-stats *before* starting to play the video. 


<br />
<br />

## Week 5: What is the typical pattern of video streaming WITH vpn?
Nov 2 - 6

### Discussion topics:
1. Checkpoint 1 - 10 mins open Q&A
2. EDA findings from last week
3. Data labels, parameter permutations, responsibilties of data scientists re: data collection
4. Halfway mark!  A look ahead.
 
 <br />

### Week 5 Participation Homework

1. Look for patterns that suggest streaming is occurring (vs. web browsing, etc)
2. Write code to extract data.
3. Feature engineer the pattern(s).
4. As before, zip and upload any new network-stats captures the new "Good Data" subfolder in Google Drive.

<br />
<br />

## Week 6: Binary Classifiers
Nov 9 - 13

### Discussion Topics:
1. Review feature engineering efforts thus far (using HW notebooks)
2. Talk through formulation of classifiers

<br />

### Week 6 Participation Homework:
1. Create a classifier that can take `network-stats` data files as input, and outputs whether or not there is video streaming.
2. Produce code in commented git repo that allows for reproduction (by Viasat) in a docker container.
   * You should be able to run your classifier on any other students' data
3. Provide classifications and confidence levels


<br />
<br />

## Week 7: Binary Classifiers
Nov 16 - 20

### Discussion:
1. Domain knowledge review
2. HW 6 review, highlighting feature engineering and ML outcomes
3. Project Proposal: Base case (binary classifier) plus extension
    * What is minimum amount of data needed to make a binary classifier?
    * What else can be classified (video provider, content, resolution, steady state vs. start up buffering, rebuffers/skips ahead in content)?
    * What can of noise can be tolerated (noise limits)?

### Assignment:
Iterate and improve your binary classifier

1.  Create a classifier that can take network-stats data files as input, and outputs whether or not there is video streaming.
    * You should be able to run your classifier on any other students’ data
    * Provide instructions in README on how to run your model
2. Produce code in commented git repo that allows for reproduction (by Viasat) in a docker container
3. Provide confusion matrix and explain what the model gets wrong using specific examples from the data
4. Submission will be 2+ Google Slides with key results, annotated
    * Include link to your GitHub model and docker container
    * Include enough code snippets to convey understanding of how results were produced


<br />
<br />

## Week 8: Binary Classifiers, Q2 Project Proposals
**<mark>NEW!</mark>**  
### Thanksgiving Week
Nov 23 - 27
### Discussion
We will be holding discussion this week!  Make sure you attend.

### Discussion:
1. Domain knowledge review
2. HW 7 review
3. Q2 Project Proposals review

### Assignment:
1. Iterate and improve your binary classifier
    * You should be able to run your classifier on any other students’ data
    * Provide instructions in README on how to run your model
2. Produce code in commented git repo that allows for reproduction (by Viasat) in a docker container
3. Provide confusion matrix and explain what the model gets wrong using specific examples from the data
4. Submission will be 2+ Google Slides with key results, annotated
    * Include link to your GitHub model and docker container
    * Include enough code snippets to convey understanding of how results were produced




<br />
<br />

## Week 9
Nov 30 - Dec 4
1. Present plan for next quarter

<br />
<br />

## Week 10
Dec 7 - 11
1. Present results to Viasat
