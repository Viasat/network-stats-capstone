---
layout: default
title: Network Performance Classification Fall 2021 Syllabus
description:  Week by week summary of assignments and goals
---

### [Home](./)

<br />

## Jump to [Current week!](#week-8)

<br />
<br />

## Week 1: Project overview and course expectations
Sep 27 - Oct 1
### Discussion topics:
*  Introductions
*  TCP/IP Networking Overview
*  Tools introduction:  Wireshark, Docker, and DANE
<br />

### Assignment:
*  Install Wireshark, capture and investigate packet data
*  Create a brief (no more than 5 slides) presentation highlighting some of your key Wireshark analysis & takeaways.  We recommend using screenshot snippets and annotating them with your notes.  Be prepared to share your findings in Section next week.

<br />
<br />

## Week 2: 
Oct 4 - Oct 8
### Discussion topics:
*  Discuss Wireshark analysis
*  Going deeper with Wireshark packet capture data

<br />

### Assignment:
*  Generate packet capture data in Wireshark and export to CSV
*  Analyze and visualize CSV data
*  Create a brief (no more than 5 slides) presentation showcasing your DANE-data visualizations and key takeaways.  Be prepared to share your findings in Section next week.

**<mark>NOTE</mark>: See [Homework 2 Detailed Instructions](Fall_2021_Week2_HW.html)**

<br />
<br />


## Week 3: 
Oct 11 - Oct 15
### Discussion topics:
*  Introduction to DANE and Docker

<br />

### Assignment:
*  Install Docker and DANE
*  Capture network traffic data with DANE and visualize it in your preferred environment (Jupyter, R Studio, etc)
*  Create a brief (no more than 5 slides) presentation showcasing your visualizations and key takeaways.  Be prepared to share your findings in Section next week.

**<mark>NOTE</mark>: See [Homework 3 Detailed Instructions](Fall_2021_Week3_HW.html)**

<br />
<br />


## Week 4: 
Oct 18 - 22  
### Discussion topics:
*  Network degradation scenarios - what are they?  Why do we care?
*  How to configure DANE to emulate degradation scenarios.
*  Looking ahead - what's to expect for the next few weeks and rest of Fall Quarter.

<br />

### Assignment:
*  Capture network traffic data with DANE for various packet loss scenarios.
*  Analyze and visualize your data in your preferred environment.
*  Identify candidate features for a model to predict packet loss.
*  Create a brief presentation showcasing your visualizations and key takeaways.  Be prepared to share your findings in Section next week.

<br />
<br />


## Week 5: 
Oct 25 - Oct 29

### Discussion topics:
*  DANE, CPU utilization, and other concurrent internet usage
*  Work in pairs?  Checkpoint 1 status?
*  Building a model to predict packet loss ratio

<br />

### Assignment:
*  Build and train a model to predict packet loss ratio.
*  Use DANE to generate as much data as you need to sufficiently train and test your model.
   *  Remember it may be better to run DANE scenarios one or two at a time, vs. try to run too many concurrently.
*  Share your progress on your model.  Summarize results in a brief presentation (as typical) but also share your notebooks, scripts, etc.


<br />
<br />


## Week 6:
Nov 1 - Nov 5
### Discussion topics:
*  Checkpoint 1 review
*  Packet Loss model review
*  Adding variability in latency

<br />

### Assignment:

*  Finish up your packet loss models
*  Start exploring how modifying latency affects your features & models
*  Propose (and define!) candidate features for predicting latency.
   * You may want to start by keeping packet loss fixed and generating data sets for various latencies.
   *  FYI cable/fiber internet services typically have latencies of 20ms or less (what's yours?).  Geostationary satellites like ours typically have a round trip (to the satellite and back) latency of 260ms or so.

<br />
<br />


## Week 7:
Nov 8 - Nov 12
### Discussion topics:
*  Review Packet Loss models
*  Latency prediction models - review candidate features
*  Summarize timeline for the rest of the quarter
   *  Begin discussion about Q2 project proposals and teams
   *  Final Replication Report and Final Presentations

<br />

### Assignment:

*  Build & train a model to detect latency, given a fixed packet loss ratio (you choose the ratio for your initial model)


<br />
<br />


## Week 8: Q2 Project Proposals
Nov 15 - 19
### Discussion topics:
*  Review latency prediction model results
*  Discuss candidate Q2 project ideas

<br />

### Assignment:
*  Extend your models to predict both latency AND packet loss
*  Use DANE to generate as much data as you need to build, train, and test your models
*  Summarize model results, including a list (and definitions!) of your features.
*  Include links to your models (notebooks, scripts, etc)
<br />
<br />


## Week 9:  Q2 Project Proposals
### Thanksgiving Week
Nov 22 - Nov 26
### Discussion topics:
We will be holding discussion this week!  Make sure you attend.

*  Finishing up your latency & packet loss classification models - your results will be documented in your Final Replication Paper.
*  Continue discussion about Q2 - project proposals and teams

<br />

### Assignment:
*  Finish up your latency & packet loss models
*  Finish up your Q2 project proposals

<br />
<br />

## Week 10
Nov 29 - Dec 3

1. Teams Present to Viasat
    * Each team delivers their elevator pitch and at least the first couple weeks of their detailed task schedule.
2. Viasat shares our expectations for next quarter.
