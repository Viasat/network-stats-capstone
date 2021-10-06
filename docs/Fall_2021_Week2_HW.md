# Week 2 Homework

Now that you have explored Wireshark a little bit, we are going to start some basic analysis with data captured in it. One of the things you likely noticed last week was that there are an enormous number of packets, and that is for just a few minutes of data on just your computer. Large files, for example, a video game, can easily exceed 10 million packets in size. As a result, Internet Service Providers never hold onto information about individual packets, instead their data collection tools aggregate packet information as it is being collected.

For this week, we are asking you to use the tool of your choice to perform such aggregation. Starting next week, you will start collecting data with a tool that outputs data in such an aggregated manner.


## Task #0: Prep Work

1.	Right click on the heading of the packet view (the top third) in Wireshark (where “time”, “Source”, “Destination”, “Protocol”, etc. are) and select Column Preferences
2.	Add three new columns: Source Port, Destination Port, and Transport Protocol. Update the Type field to match what is displayed in the screen capture. Then update Fields and Field Occurrence for “Transport Protocol” to match the screen capture (these might not be editable until a type of Customer is selected). Click OK.
 
!(Figure 1)[img/hw2fig1.png]

3.	Capture some data with Wireshark, as you did last week
4.	To make things interesting, try watching a video or downloading a file after the capture had been going for several seconds
5.	Collect about 5 minutes worth of data (doesn’t have to be exact), then stop the capture (red square in top-left)
6.	In Wireshark: `File` -> `Export Specified Dissections` -> `CSV…`
7.	In the window that appears, make sure to select “All Packets” and “Captured” and try to match the Packet Format section

!(Figure 2)[img/hw2fig2.png]

8.	Ingest into analytics tool of your choice (read on for requirements to help you choose the right tool)
9.	Do not close Wireshark! Or, before you do, make sure to save the capture somewhere, so you can re-open it. You will need this capture in Wireshark 


## Task #1: Per-Second Aggregation

For every second represented in the file, compute the sum of bytes (Length) transferred in that second and the count of the number of packets (every line in the file represents a packet).

Create two time series graphs, one for bytes and one for packets.

Check your work with Wireshark by:
1.	`Statistics` -> `IO Graphs`
2.	Select a Y Axis of Packets and an Interval of 1 sec

!(Figure 3)[img/hw2fig3.png]

3.	Get screen capture
4.	Double-click on ‘Packets’ to bring a drop-down window and select ‘Bytes’
5.	Get screen capture
There might be slight differences, but your graphs and Wireshark’s should be pretty similar.
Turn in a PowerPoint, Word, PDF, etc. with your and Wireshark’s Byte time series side-by-side and your and Wireshark’s Packet time series side-by-side.


## Task #2: Per-Connection Aggregation

A connection is a single conversation. Think of it as being similar to how threads work: a single thread is only performing a single task sequentially, but a bunch of threads can get timeshared onto a single core. Similarly, several connections will get timeshared onto a network connection. For those with a bit of network programming experience: every time a client opens a new socket, it is creating a new connection.
A connection is uniquely identified by 5 factors (among networking folks, we call this the “5-tuple”):
* Source IP address (shown as Source in Wireshark’s csv)
* Destination IP address (shown as Destination in Wireshark’s csv)
* Transport Protocol
* Source Port
* Destination Port

Source Port and Destination Port only make sense when the Transport Protocol is “TCP” or “UDP”. When the transport protocol is neither, the field will either be blank or nonsense.

In database terms, you can think of those 5 pieces, all together, representing a primary key. However, there is a catch. When you send to Google, your address is the source and Google’s address is the destination. However, when Google sends a reply back it you, their address is the source and your address is the destination. This is still the same connection! The ports will swap in exactly the same way.


### Examples:
The same connection: 
```
Src: 192.168.1.1 Dst: 4.2.2.2 Transport Proto: TCP Src port: 50000 Dst port: 443
Src: 192.168.1.1 Dst: 4.2.2.2 Transport Proto: TCP Src port: 50000 Dst port: 443
```

The same connection (IP and port swapped):
```
Src: 192.168.1.1 Dst: 4.2.2.2 Transport Proto: TCP Src port: 50000 Dst port: 443
Src: 4.2.2.2 Dst: 192.168.1.1 Transport Proto: TCP Src port: 443 Dst port: 50000
```


Different connections! (IP swapped, but port did not):
```
Src: 192.168.1.1 Dst: 4.2.2.2 Transport Proto: TCP Src port: 50000 Dst port: 443
Dst: 192.168.1.1 Src: 4.2.2.2 Transport Proto: TCP Src port: 50000 Dst port: 443
```


The same connection (other than TCP or UDP, just compare IP and protocol):
```
Src: 192.168.1.1 Dst: 4.2.2.2 Transport Proto: ICMP Src port: N/A Dst port: N/A
Dst: 192.168.1.1 Src: 4.2.2.2 Transport Proto: ICMP Src port: N/A Dst port: N/A
```

<br />
Create an output that, for every connection, indicates the sum of bytes and count of packets associated with that connection.

In Wireshark, `Statistics` -> `Conversation`, then select the TCP tab or UDP tab. Ensure that there is a connection with a value greater than zero in the “Packets A->B” and “Packets B->A” columns. Take a screen capture. 

In your output, find a connection that was visible in the Wireshark screenshot (and non-zero values in the Packets A->B and B->A columns). Take a screen capture.

Highlight the connection that is visible in both screenshots. Put side-by-side in Powerpoint, Word, PDF, etc.

The Packets and Bytes column values will be the same between Wireshark and your code, if your code is working properly.
