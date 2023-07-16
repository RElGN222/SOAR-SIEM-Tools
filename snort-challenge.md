# Scenario 1 | Brute-Force
First of all, start Snort in sniffer mode and try to figure out the attack source, service and port.

Then, write an IPS rule and run Snort in IPS mode to stop the brute-force attack. Once you stop the attack properly, you will have the flag on the desktop!

Here are a few points to remember:

Create the rule and test it with "-A console" mode. 
Use "-A full" mode and the default log path to stop the attack.
Write the correct rule and run the Snort in IPS "-A full" mode.
Block the traffic at least for a minute and then the flag file will appear on your desktop.


# START
To begin, I ran Snort to capture and display packet payloads since I wasn't sure what to expect. The command I used was: sudo snort -X.

I let it run for approximately 30 seconds, then interrupted the process using CTRL+C to examine the payload. One payload caught my attention—someone seemed to be attempting to gain access through SSH.

Next, I navigated to the rules folder using cd /etc/snort/rules and created a file called local.rules using nano local.rules. Inside the file, I added the following rule: alert tcp (suspicious ip) any <> any any (msg: "suspicious ip"; sid: 1000001; rev: 1;). I then ran this rule for another 30 seconds to generate a log file for better analysis. To do this, I used the command: sudo snort -c local.rules -A full. Run this command for approximately 30 seconds.

Opening a new terminal, I switched to the logs directory using cd /var/logs/snort (Note: you may need to check the exact directory). Considering the permissions required to read the logs, I preemptively changed ownership using the command: sudo chown ubuntu /var/logs/snort. Confirm the username with whoami to ensure ownership transfer. By changing the ownership, any files created in this directory will be accessible to us. I examined the log file using sudo snort -r snort.log.(numbers) -X to verify my suspicions. It appears that this IP address is attempting to establish a connection with us.

Returning to the rules, I modified them to use "reject" instead of "alert." In the local.rules file, I replaced the rule with: reject tcp (suspicious ip) any <> any any (msg: "reject suspicious ip"; sid: 1000002; rev: 1;). After saving the changes, I executed the rule using sudo snort -c /etc/snort/rules/local.rules. It should take effect within a minute.

Challenge Questions:

Stop the attack and retrieve the flag (which will appear on your Desktop).
Answer: THM{81b7fef657f8aaa6e4e200d616738254}

What is the name of the service under attack?
Answer: SSH

What is the protocol/port used in the attack?
Answer: TCP/22

Task 3 Scenario 2 | Reverse-Shell

In this scenario, I followed the same initial steps as in the previous scenario. I ran Snort with the -X option to view the payload. I noticed a suspicious payload containing our username and IP address. Additionally, it was heading towards port 4444, which is commonly associated with rootkits for backdoor access—raising concerns.

Navigating to the rules folder using cd /etc/snort/rules, I created a local.rules file using nano local.rules and added two rules:

reject tcp any any <> (suspicious ip) any (msg: "reject suspicious ip"; sid: 1000001; rev: 1;)
reject tcp any any <> any 4444 (msg: "reject commonly used backdoor port"; sid: 1000002; rev: 1;)
My intention was to block traffic to the suspicious IP, preventing any outbound communication, and also block port 4444 due to its association with commonly used backdoor access. I executed this new rule with sudo snort /etc/snort/rules/local.rules -A full, and it should take effect after a while.

Challenge Questions:

Stop the attack and retrieve the flag (which will appear on your Desktop).
Answer: THM{0ead8c494861079b1b74ec2380d2cd24}

What is the protocol/port used in the attack?
Answer: TCP/4444

Which tool is highly associated with this specific port number?
This question may require some online research.
Answer: Metasploit

