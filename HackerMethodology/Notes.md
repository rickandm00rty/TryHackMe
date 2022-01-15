|Hacker Methodology Notes - Kyle Nelson Jan 2022|
=================================================
I wanted to take these notes as I was having troubles starting new rooms and understanding where I should start other
than a simple NMap scan....What are the next steps? How do I use tools to connect to machines and explore? 

|Recon|
=======
Genreally speaking, this involves no direct interaction with the target. This should be the most familiar to people as
it simply means researching the web for information on your target. Tools can include the following:
    
    Google (specifically Google Dorking) - Highly specific and tailored Google searches (Wildcards, operators, etc..)
    Wikipedia
    PeopleFinder.com
    who.is
    sublist3r - Tool for analyzing subdomain info
    hunter.io
    builtwith.com
    wappalyzer


|Enumeration & Scanning|
========================
Scanning the target directly to gather information.The goal of this is to define the possible 'attack surface' of a target.
    
    |Tools include|
    ===============
    dirb - Scan file directories on a given address or site
    metasploit - Automatic Vulnerability Finder/Script Implementer
    nmap
    exploit-db - Contains a bunch of known explots ready for use on a target
    Burp Suite - Interecept and inject HTTP and HTTPS traffic
    And many, many others

    |Typical NMap Scan Reference|
    =============================    
    Basic subnet Ping Scan - nmap -sp 192.168.1.1/24
    Scan Single Host - nmap google.com
    Stealth Scan - nmap -sS (only processes 2 out of 3 handshakes requests which verifies open ports without the defender 
        seeing the connection on their end
    Version Scanning - nmap -sV google.com
    OS Scanning - nmap -O google.com
    Aggressive Scan (All-in-one) - nmap -A google.com (this is easily detected by the defender, but is the lazy way)
    Specify Port (flag can be added to other scan types) - nmap -p "port" google.com
    Verbose Output of Scan (flag can be added to other scan types) - nmap -v google.com

|Privelege Escalation|
======================
This phase is started once basic access to a machine has been made. This could be a user account or unpriveleged shell.
    
    |Takes the following forms|
    ===========================
    Cracking Password hashes
    Vulnerable service that has privileges
    Re-using discovered passwords (or password library)
    Default credentials
    Command Injection for Online Forms or Logins
    Automated Scripts that find Exploits 

|Reporting|
===========
Essentially gathering how the exploit was done and potential cleanup options and fixes as well as WHY it's a critical vulnerability

Not much in this section as I likely won't have an opportunity to create one through Try Hack Me or my personal exploting. 






