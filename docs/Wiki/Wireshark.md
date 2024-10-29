---
tags:
  - forensics
---
Wireshark is the most commonly used network protocol analyser and the de facto standard across many commercial and non-profit enterprises.

**Some notable features:** Shows the protocol of each packet captured and also the protocol hierarchy of the network whose pcap was made. The hex buffer of each packet can be analysed separately and layer by layer.

### Installation
	sudo apt install wireshark-qt

**Let's try analysing a pcap file**
This challenge came as part of a high school CTF(Angstrom CTF 2018).

The given is a pcap file that has many protocols like DNS, ICMP, TCP etc. By analysing the file closely using pcap we can see that there are 28 packets out of which there are 2 HTTP packets.

![[wireshark_1.png]]

The two rows below the packet list show us details regarding the packet structure and also the buffer data in each packet respectively. The first row shows the packet structure of each packet in a capture.

By double-clicking and selecting a particular packet a detailed view of the different layers of a packet can be viewed.

![[wireshark_2.png]]

The second row shows the buffer data that is transferred through the network in each packet. For example, in the packet where the PNG image is transferred will have the image data present in the buffer that was transferred through the network as shown.

![[wireshark_3.png]]

For any transfer of packets occurring in a network each of the packets transferred has a hierarchy of layers followed as per the OSI model for a network. Wireshark allows you to examine the protocol hierarchy of a packet capture. For doing so go to  **Statistics>>Protocol hierarchy** on the toolbar.

![[wireshark_4.png]]

Of the given challenge's pcap we can see that there are 7 columns that show the packet number the source and destination IP of a particular packet and also the protocol followed by the image and the time and an info about the packet and also the bytes of data transferred in the packet under the length.

Since HTTP protocol is concerned with specifying the format and transmission of messages, the chance of any multimedia being transferred in these packets is high. Hence using Wireshark we can analyse and dump if any multimedia is transferred through these packets. For doing so go to: **File>>Export Objects>> HTTP**.

By doing so we get a dialogue box as shown.

![[wireshark_5.png]]

This a list of all multimedia files transferred in these stream of HTTP packets. By saving this image and opening we get the flag as the image.

**Flag: actf{0ver_th3_w1re}**
![[wireshark_flag.jpg]]