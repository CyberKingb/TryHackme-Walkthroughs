# Zeek

# Task 1 (Introduction)
Zeek (formerly Bro) is the world's leading platform for network security monitoring. Flexible, open-source, and powered by defenders." "Zeek is a passive, open-source network traffic analyser. Many operators use Zeek as a network security monitor (NSM) to support suspicious or malicious activity investigations. Zeek also supports a wide range of traffic analysis tasks beyond the security domain, including performance measurement and troubleshooting."



The room aims to provide a general network monitoring overview and work with Zeek to investigate captured traffic. This room will expect you to have basic Linux familiarity and Network fundamentals (ports, protocols and traffic data). We suggest completing the "Network Fundamentals" path before starting working in this room. 



A VM is attached to this room. You don't need SSH or RDP; the room provides a "Split View" feature. Exercise files are located in the folder on the desktop. Log cleaner script "clear-logs.sh" is available in each exercise folder.

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/e194b343-829d-44c3-9f23-5c52cccfa7e9)


To start the machine click on the start machine button.

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/8581d0a0-efa5-4e2b-a1d5-91e3a289b3fc)

For the first question click on completed

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/a244d076-2eef-4bd1-94e2-8cd3a89ee409)

# Task 2 ( Network Security Monitoriing and Zeek )

##  Working with Zeek

There are two operation options for Zeek. The first one is running it as a service, and the second option is running the Zeek against a pcap. Before starting working with Zeek, let's check the version of the Zeek instance with the following command: `zeek -v`

Now we are sure that we have Zeek installed. Let's start the Zeek as a service! To do this, we need to use the "ZeekControl" module, as shown below. The "ZeekControl" module requires superuser permissions to use. You can elevate the session privileges and switch to the superuser account to examine the generated log files with the following command: `sudo su`

# Questions


## Question 1 **(Each exercise has a folder. Ensure you are in the right directory to find the pcap file and accompanying files. `Desktop/Exercise-Files/TASK-2`)**
