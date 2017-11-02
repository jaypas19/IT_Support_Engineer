# IT Support engineer Questions


## How to submit the answers

1. Create a GitHub Account
1. Git Clone this repository to your local machine
1. Remove the current `origin` remote (`git remote remove origin`)
1. Create a new repository under your GitHub account (do **NOT** fork this repository)
1. Follow the instructions to `push an existing repository from the command line...`
1. Create a branch called `add_answers` on your local machine
1. Add answers to this Document (using a simple Text editor), commit your answers to the `add_answers` branch
1. Push your `add_answers` branch to your personal remote `origin`
1. Send a notification to your contact at Honestbee with a link to your repository

If any of the steps above is unclear, please try GitHub user guides first, then ask your contact at Honestbee to clarify. 

The method of submission is part of the test (usage of Git) - but we won't use `forks` or `pull requests`. 

## Questions

1.  A vendor is trying to connect to a server we publicly expose (assume we are not using VPN). When asked for his public IP from which he will be connecting, the vendor provides us with the following IP `192.168.0.100`, what should be our next steps? 

    1.  Include questions we may need to ask to get additional information to ensure this vendor will be able to connect over the public internet to our server. __Note that this vendor is not in our LAN, nor on a VPN with us__.

        > Add follow up Questions here as a bulleted list and add an explanation why you ask each question (what do you expect to receive back)

        1.  Example Follow Up Question 1

 - The IP Address you have provided seems to be your LAN IP Address. Can you direct us to the right person or someone from the IT Department who can  provide us with the complete details of your Internet Subscription please. You can also check your complete IP Address details with your ISP.  
            Explanation for Example Follow Up Question 1
        
- Since the IP address provided by the vendor is not the right IP Address, I pressume that the vendor that is trying to connect to the publicly exposed  server is not from the IT department, hence, in order to get the correct information it is better to ask who is the right person to talk to. Checking  with their ISP is also an option.

        1.  Example Follow Up Question 2
        
- Is your Public IP Adress Static or Dynamic? 
Explanation for Example Follow Up Question 2
- The Question 2 is assuming that the correct Public IP Address has already been provided. Allowing access for a Dynamic IP Address will require  modification everytime the IP Address changes while allowing access for a Static IP Address can be done only once since the IP address does not  change.


    1.  Write a PowerShell command (assume Windows 2012 R2) to add a new firewall rule on a single server, allowing incoming connections on port `3389` for `TCP` protocol __limited to the public IP of the vendor only__ (assuming we have the public IP of the vendor)

    ```powershell
    # PS C:\> New-NetFirewallRule -DisplayName "Allow Vendor Public IP Address on TCP  Port 3389" -Direction Inbound -Action Allow -RemoteAddress 192.30.255.113 -Protocol TCP -LocalPort 3389 
    ```

1.  How do you list all Computers in an Active Directory Domain using Powershell (output DNSHostname in a table format, no need for `filters` or `SearchBase`)

    ```powershell
    # PS C:\>Get-ADComputer -Filter * | Select -Property DNSHostName | Export-CSV "C:\AllComputer.csv"
    ```

1.  What could possible troubleshoot tests be for the following output on a macOS machine. 
    
    For each step, mention what would be your next step

    ```bash
    $ ping microsoft.com
    PING microsoft.com (23.100.122.175): 56 data bytes
    Request timeout for icmp_seq 0
    Request timeout for icmp_seq 1
    ...
    ```

    Notes:

    -   Local machines in the same network can still be pinged by IP


a. Visit another website or ping another website. if you can ping or visit another website, most likely microsoft.com has a problem or the site is down.
	b. If you cannot also ping or visit the other website successfully, try other machine on the network to ping microsoft.com and check other websites too. If you proved that the other machine has an internet, the first machine is at faulty. If all other machines cannot successfully ping microsoft.com or cannot browse the internet, the internet link is down and there is a need to check the internet connection link.
c. If microsoft.com is pingable from other computer on the network, try using the Network Diagnostics  feature of the MacOS machine. (Apple menu > System Preferences. Select Network>Assist me>Diagnostics) Sometimes the utility can repair the problem.
d. Try turning the WiFi Off and On for wireless connected machine and unplugging and plugging backed in the patch cable for wired connected machines.
e. Try restarting the machine, restarting a machine could save you a lot time troubleshooting a faulty machine :) (Proven many times).
f. Check IP settings for any misconfigurations like static IP address that has been set. Possible no gateway and DNS setting for static IP.
g. If all workarounds do not work at all, the last resort would be to reinstall the MacOS. Backup all the required files before doing so.


Thank you for your time.
