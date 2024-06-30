# Brim Room on Tryhackme
BRIM is an open-source desktop application that processes pcap files and logs files. Its primary focus is providing search and analytics. In this room, you will learn how to use Brim, process pcap files and investigate log files to find the needle in the haystack!

This room requires you to have knowledge in networking and zeek.

## Task 1
Start the machine.

<img width="937" alt="Task" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/57eb458b-0a93-4eb9-9118-7932323a9ab1">

## Task 2
Just go through the writeup and click on completed 

![Task 2](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/546fd6e2-dde5-4c30-82da-c27326d432a8)

## Task 3
Go through the write up properly.
### Question 1
Process the `sample.pcap` file and look at the details of the first DNS log that appear on the dashboard. What is the **qclass_name**?

### Solution
Go to your launched machine and open up brim.

<img width="330" alt="opening up brim application" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/46a6548f-0d06-4161-8a10-3ceeb353dda9">

Click on choose file and then in the `Desktop` folder navigate to the `Exercise-File` folder to open `sample.pcap`

![choosing the file 1](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/fb7fabc2-e7bd-4a40-8644-39bb86bbc530)

![Choosing the file 2](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/e9d3749e-ff3e-4ea0-9a5d-552000dc7638)

<img width="784" alt="Choosing the file 3" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/8026ae6e-eda1-4770-8536-9e7b50282223">

![image](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/752a2c84-a34c-4ef3-a329-b1a2f337fd7e)

If you look at the brim dashboard you'll see the first DNS File, click on it, then at the right side of the dashboard youll see the **Log Details** scroll down and you'll see **qclass_name** is `C_INTERNET`

<img width="926" alt="qclass_name" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/a44a2538-8b40-4b1c-aa83-0bca364553bd">

![Solved](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/1c75be46-922a-4e09-a498-f2214a8b012c)

### Question 2
Look at the details of the first NTP log that appear on the dashboard. What is the `duration` value?

### Solution 
On your dashboard you'll see the first ntp file click on it on the **Log Details** scroll down and look for duration and you'[ll find that its `0.005` seconds.

<img width="231" alt="duration" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/5749817f-382a-4afe-b5a3-15ca9cd8c3f9">

![solved](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/4eb6b351-5a08-48e7-bbce-9c6ec9915d81)

### Question 3
Look at the details of the **STATS** packet log that is visible on the dashboard. What is the `reassem_tcp_size`?

### Solution
On your Brim dashboard look for the **stats** log, then scroll down on the Log details and you'll see that the **reassem_tcp_size** is `540`

<img width="760" alt="reasse_tcp_file size" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/8732e8c7-26bb-498c-89d1-f3ff51cddf23">

![Solved](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/e84275ff-7811-4797-a12d-cbcc10212150)


## Task 4 (Deafult Querries)
Brim unlike Zeek makes adding queries very easy.

### Question 1
Investigate the files. What is the name of the detected GIF file?

### Solution
On your Brim dashboard look for the **Local Lake** section and click on add file button and import the task 4 file.

<img width="207" alt="Adding task 4 file" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/cb488ed4-5a7d-410d-86db-6cb46ebfa51a">

On the Queries section click on the **File Activity** Query

<img width="206" alt="Query" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/2ccec9c6-d7b9-4022-a6e7-a2d4f57c612e">

It'll filter the logs and only bring out the file logs look at the **mine_type** row youll find the **image/gif**

<img width="540" alt="Gif file" src="https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/0ff0035d-7e7a-43ab-9d0d-d1d4b15ab3bf">

Click on the log and check the details youll find the filename to be `cat01_with_hidden_text.gif`

![filename](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/7731ba87-e739-45b9-9c36-f1ea8c521563)

![Solved](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/b632c86e-1a00-4496-8edf-81738b01c982)

### Question 2
Investigate the conn logfile. What is the number of the identified city names?

### Solution
On the Brim dashboard in the query input field put in `_path=="conn" | cut  geo.resp.city | sort -r`
It'll bring out 2 Cities.  

![2 cities](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/d2e28343-3c62-457b-a9af-c421fffa851c)

![Solved](https://github.com/CyberKingb/TryHackme-Walkthroughs/assets/161872623/36abc68f-0b1f-41d1-99f7-13b12594fa64)

### Question 3
