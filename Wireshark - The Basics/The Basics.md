WIRESHARK: The Basics
Wireshark is an open-source, cross-platform network packet analyser tool capable of sniffing and investigating live traffic and inspecting packet captures (PCAP).
There are multiple purposes for its use:
Detecting and troubleshooting network problems, such as network load failure points and congestion.
Detecting security anomalies, such as rogue hosts, abnormal port usage, and suspicious traffic.
Investigating and learning protocol details, such as response codes and payload data.

Activity description: Getting familiar with the basic tools and functions of Wireshark.
Tools used: VM, wireshark, .pcap files
Methodology:
Tool overview - By clicking on the details button at the bottom left of the page, I was able to read the file’s comments and find the values required by the exercise.
Packet dissection - By opening packet 38’s details, I was able to analyse its data on each OSI layer and find the required values, such as the markup language used, the date of arrival, the TTL value and the TCP payload size.
Packet navigation – By using the “Go to packet” and “Find packet” tools I was able to find the requested data requested in the exercise, filtering by the number of the packet, the info contained in it and its format. Moreover, analysing the “expert tool” window, I could find the exact number of warnings in the file.
Packet filtering – Filtering the captures by using different techniques like “Apply as filter”, “Conversation filter”, “Apply as column", “Follow stream”, and by filtering by Protocol Name or Port.
Lessons Learned: I learned how to read a file comment and how to investigate a packet content searching through its details. Moreover, I learned how to navigate within the list of captures by looking for specific lines or by filtering by the value of interest.


