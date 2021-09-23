# Introduction

Can machine learning predict when a network user would perceive a degradation of their network's performance?

Students will generate data of network traffic under a variety of network degradation conditions, then build models to detect network issues as they are perceived by users and their devices, not just network speed (and other metrics) between the service provider’s network and the user’s modem.  This will enable service providers to work with their customers to ensure that their actual experience with the Internet is as good as the network can deliver.  This project will use (and possibly extend) a network emulation & data collection tool developed by an HDSI Capstone team last year to generate data and emulate network conditions.


# Fall 2021 Syllabus
[Fall 2021 Syllabus](Fall_2021_syllabus.html) - for a week-by-week summary of assignments and goals.


## First Quarter Assignments/Goals:

Students will learn about basic TCP/IP networking fundamentals, and will explore several different network degradation scenarios.  Initially we will narrow our exploration to a small number of scenarios, and generate labeled data of the network under these scenarios.  Students will create binary classifiers to detect whether the network degradation scenario is happening.  (For example, whether a data stream represents separate file downloads vs. one single file with missing packet(s), or whether the sender is done sending data vs. there is data being lost in transmission).


1. Preparation:
  * Work through resources provided in the background information 
  * Read documentation and install the necessary tools
    * Wireshark [https://www.wireshark.org/](https://www.wireshark.org/)
    * Docker [https://docs.docker.com/get-started/](https://docs.docker.com/get-started/)
    * DANE [https://github.com/dane-tool/dane](https://github.com/dane-tool/dane)
2. Create data sets:
  * Using DANE, an open-source tool initially developed by UCSD HDSI capstone studnets in Winter 2021, to emulate various network conditions and generate data about network packet traffic.
3. Analyze:
  * Perform exploratory data analysis, feature engineering.
4. Machine Learning:
  * Build classifiers to identify current network conditions



# Mentorship and Guidance
## Discussion Sections
**Wednesdays 10:00a - 10:50a Pacific**.  We meet in SDSC 129E and on Zoom.


## Office Hours

### TA Office Hours
TBD

### Viasat Office Hours
The office hours for this capstone project will be **Fridays 9:00a - 11:00a** Pacific.  During that time there will be 1+ Viasat mentors available to quickly respond to questions posted in Slack, and/or to jump on Slack/Zoom/etc calls as needed.

During the week you may also use Slack to ask questions in the group channel, and/or to any of us privately.  We may not be as quick to respond due to meetings and other obligations, but we will respond in a reasonable amount of time.  Also, please use each other to ask and answer questions.

We are all in this together!

<br />
<br />
<hr />
<br />

# Background Information
The primary tool used for data collection will be an open-source utility called DANE, which was originally written by UCSD HDSI capstone students in Winter 2021.  This tool allows you to run experiments with different network conditions that affect network traffic performance.

Students will need to become familiar with the basics of networking.  **Here are a few resources to get started:** 

### General Networking:
PBS has created a series on computer networking that does a good job of explaining the what and why, rather than getting caught in the details on the how:  
[https://www.youtube.com/watch?v=3QhU9jd03a0](https://www.youtube.com/watch?v=3QhU9jd03a0) (watch at least from 6:30 to the end)
[https://www.youtube.com/watch?v=AEaKrq3SpW8](https://www.youtube.com/watch?v=AEaKrq3SpW8) (watch at least from beginning to 8:00)


### Networking architecture:
Wikipedia pages for TCP, UDP, and OSI 7 layer model
[https://en.wikipedia.org/wiki/Transmission_Control_Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)  
[https://en.wikipedia.org/wiki/User_Datagram_Protocol](https://en.wikipedia.org/wiki/User_Datagram_Protocol)  
[https://en.wikipedia.org/wiki/OSI_model](https://en.wikipedia.org/wiki/OSI_model)

