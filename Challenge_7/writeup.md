Problem Description:

The challenge was based on a real-world cybersecurity scenario where a company suspects that someone logged into their internal portal without authorization.

The only evidence provided was:
A network capture file (.pcap)
A login page that is still active.

The instructions clearly mentioned that the flag is hidden inside the system, and the goal was to:
Analyze the network traffic
Find stolen login credentials
Log into the system
Retrieve the hidden flag
This task mainly focused on packet analysis, understanding how credentials travel over the network, and thinking like an attacker.

My Initial Understanding:

At first, I honestly felt confused because I had never worked with a .pcap file before.
I knew in theory that packets carry data, but I didn’t know how to actually read them.
So instead of jumping into the solution, I first asked myself:
What is a PCAP file?
How are login details sent over the network?
What tools are used to analyze network traffic?
I realized this task was more about learning how to observe, not rushing to the answer.

Tools Used
To solve this task, I used the following tools:
Wireshark – for analyzing the .pcap file
Web Browser – to access the login page
Basic HTTP knowledge – to understand GET vs POST
Given source files – to understand how the backend works
Wireshark was completely new to me, so learning it was part of the task itself.

Step-by-Step Approach
Learning What a PCAP File Is

Before opening the file, I searched and learned that:
A .pcap file stores captured network packets
These packets may contain requests, responses, headers, and sometimes raw data
If traffic is not encrypted, sensitive data can appear in plaintext
This gave me a direction to move forward.

2️.Opening the PCAP File in Wireshark

After installing Wireshark, I opened the provided file login_capture.pcap.
At first, the screen was filled with many packets and it looked overwhelming.
I realized that not all packets are important, just like the hint suggested.
So I started filtering.
3️Filtering HTTP Traffic
Since the task involved a login page, I thought the credentials would be sent using HTTP.
I applied this filter:
http
This immediately reduced the noise and showed only HTTP-related packets.
This step was important because it helped me focus only on what matters.
Finding the Login Request
After filtering, I looked closely for:
POST requests
Requests sent to the /login endpoint
I learned that login forms usually use POST, not GET, because credentials are submitted in the request body.
Once I clicked on the POST request, I inspected the packet details.
 Discovering the Credentials (Key Moment)
While expanding the packet details, I found the form data sent during login.
To my surprise, the credentials were visible directly as text:
username=isitadmin and password=iamtheadmin

This was the exact moment I understood the vulnerability.
The credentials were sent in plaintext, meaning anyone capturing traffic could read them.
 Understanding the Vulnerability
The main issue here is that the application uses HTTP instead of HTTPS.
Because of this:

Login credentials are not encrypted
Network sniffers can capture usernames and passwords
Unauthorized access becomes easy
This task helped me practically understand why HTTPS is critical, not just theoretically.

Logging into the System

After extracting the credentials, I opened the login page in the browser and entered:
Username: isitadmin
Password: iamtheadmin

The login was successful, and I was redirected to the welcome page.

Retrieving the Flag:
=Once logged in as the admin user, the application displayed the hidden flag:

FLAG{analyzing_is_imp}
