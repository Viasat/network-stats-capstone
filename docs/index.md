# VPN X-Ray

## Introduction

Can machine learning predict when a network user is streaming video through a VPN?

## Background Information
The primary tool used for data collection will be an open-source python script provided by Viasat called [Network-Stats](https://github.com/viasat/network-stats). This tool allows a student to connect to a local interface on their machine and then spits out second-by-second data for how many bytes and packets flow in each direction (upload/download) for each ‘connection’ (connection here means the 5-tuple of local and remote ip addresses and ports, as well as the protocol bit).

Students will need to become familiar with the basics of networking, how a VPN works, and how video streaming works.  Here are a few resources to get started: 

### General Networking:
PBS has created a series on computer networking that does a good job of explaining the what and why, rather than getting caught in the details on the how:
https://www.youtube.com/watch?v=3QhU9jd03a0 (watch at least from 6:30 to the end)
https://www.youtube.com/watch?v=AEaKrq3SpW8 (watch at least from beginning to 8:00)

### VPN:
https://www.youtube.com/watch?v=CuxyZiSCSfc (entire video)
Note: In larger  businesses, VPNs connect office locations of the same company together – not just between companies like talked about in the video.
 
### Video Streaming:
Good references on how video streaming works is almost impossible to find (it is a topic so obscure that most resources you find are oriented toward developers/professionals in streaming, which is far too deep for what we want to do). The following video at least it conveys some of the basic concepts well enough:
https://www.youtube.com/watch?v=9rAPDwGQK5M (just 0:30 to 4:30 – the rest is marketing material for the folks who made the video)

### Networking architecture:
Wikipedia pages for TCP, UDP, and OSI 7 layer model
https://en.wikipedia.org/wiki/Transmission_Control_Protocol
https://en.wikipedia.org/wiki/User_Datagram_Protocol
https://en.wikipedia.org/wiki/OSI_model


## First Quarter Assignments/Goals:
The first task will be to say whether or not a given VPN session contains streaming (Netflix, YouTube, etc.). If this works well, we can start getting more specific by identifying the streaming provider. We might also be able to identify other kinds of traffic like VoIP/VTC or web browsing.

The students can simply fire up Network-Stats, start watching their favorite Netflix show, and then look at the data generated.  Doing this enough times should start revealing the structure of this signature. Once the signature is better understood, students can repeat the experiment, but do so inside a VPN tunnel (provided by UCSD) and notice the signature distortion, if any. They can also add noise to the signal by doing other things while watching tv, like browsing the web, catching up on email or interacting with social media. 

How much noise does this really add? When is the initial signature no longer recognizable? These questions will have to be answered in more precise terms as the students use ML techniques to build classifiers to automatically detect these signatures.

The hope is that the signature created by a given activity on the internet – like streaming – should be unique enough as to distinguish it from other activities. If we can learn these signatures, and the overhead of the VPN tunnel and other ‘noise’ present in the tunnel don’t significantly alter the signature, then we should be able to say whether or not a given activity is happening within a given tunnel.

1. Preparation:
    * Work through resources provided in the background information 
    * Read documentation and install Network-Stats software
        * https://github.com/Viasat/network-stats
2. Create data sets:
    * Use Network-Stats on 5-minute video segments
    * Explore different providers
    * Explore different content types/formats/resolutions (tv shows, movies, codec, etc.)
    * With and without VPN
    * With and without “noise” (content only vs. content while web browsing, gaming, etc.)
3. Analyze:
    * Determine signature of video in content only mode
    * Look at steady state vs. start up buffering
    * Look at rebuffers/skips ahead in content 
    * Characterize packet and byte sizes and counts, interpacket intervals, etc.
    * Repeat steps with noise present (video + web browsing, etc.)
4. Machine Learning
    * Build a classifier to label streaming vs no-streaming without noise
    * Build a classifier to label streaming vs no-streaming with noise
5. Ethical considerations:
    * People use VPNs for a reason. What issues arise when we start weakening the ‘P’ in VPN? How far can we take this technology? What should we disclose?
