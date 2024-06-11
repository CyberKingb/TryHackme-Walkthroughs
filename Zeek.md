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


## Question 1 
**Each exercise has a folder. Ensure you are in the right directory to find the pcap file and accompanying files. `Desktop/Exercise-Files/TASK-2`**

### Solution

- Head on to the machine, 
- Open Command line.
- Input `cd Desktop/Exercise-Files/TASK-2`

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/e8e2823d-a215-4e4c-b590-47234d0c8a6f)

- Go back to the task questions and click on complete.

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/e7d3b73a-c3f7-4de1-944f-128015370f8e)

## Question 2
**What is the installed Zeek instance version number?**

###  Solution

- On your machine's Command Line input the command `zeek -v`
- You'll get zeek version `4.2.1`

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/0d27bd7b-738d-4205-b4ea-80f72fbf2f8a)

## Question 3
**What is the version of the ZeekControl module?**

### Solution
- On your Command line run `zeekctl`
  
![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/85026950-f6f4-42f3-9e80-caaa035d0340)

- To exit zeek module input `exit` into the command line..

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/a17cdac4-147f-4cae-b913-299b0d46f924)


## Question 4
**Investigate the ***"sample.pcap"*** file. What is the number of generated alert files?**

### Solution

- Back to your command line input `zeek -C -r sample.pcap`
- Input `ls -l`

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/aee45150-a717-40ef-88a2-b1702de1bdc1)

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/83925909-116f-4576-bf44-93ccb5f1fec4)


# Task 3 (Zeek Logs)

Zeek generates log files according to the traffic data. You will have logs for every connection in the wire, including the application level protocols and fields. Zeek is capable of identifying 50+ logs and categorising them into seven categories. Zeek logs are well structured and tab-separated ASCII files, so reading and processing them is easy but requires effort. You should be familiar with networking and protocols to correlate the logs in an investigation, know where to focus, and find a specific piece of evidence.

## Question 1
**Each exercise has a folder. Ensure you are in the right directory to find the pcap file and accompanying files. `Desktop/Exercise-Files/TASK-3`**

## Solution
- Go to your virtual machine, open up Terminal and input the command `cd Desktop/Exercise-Files/TASK-3`

- ![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/2f60ece7-f5f8-4ba6-8382-505e81cd7788)
- ![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/4141ac3a-fd33-4b2f-bffa-ff20e84930f6)

## Question 2
**Investigate the `sample.pcap` file. Investigate the `dhcp.log` file. What is the available hostname?**

## Solution

- On Terminal input the command `zeek -C -r sample.pcap`
- Then input `ls -l`
- Next input the command `cat dhcp.log`
- ![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/d0b5bbe7-6074-41be-b8ca-02d2d42335c0)
- ![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/2850cca9-232b-4434-bd82-e38903f7df26)

## Question 3
**Investigate the `dns.log` file. What is the number of unique DNS queries?

## Solution
- On the terminal in your machine input the command `cat dns.log`

<img width="873" alt="image" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/b64c96bc-7f5d-49bd-86c4-c15a01227faf">

-You'll see that only `2` addresses were found.






