# Snort Basic setup

when starting up snort for the first time, we should ensure the configuration file is valid.
-t is used to test configuration, and -c makes a new configuration file

<img src="https://i.gyazo.com/829b48746afe86d8cc03922fa279bfa4.png" width="400">

# Sniffer mode

Like tcpdump, Snort has various flags capable of viewing various data about the packet it is ingesting.
<br> Sniffer mode parameters are explained in the table below;

<img src="https://i.gyazo.com/d92eebc302b044e4f16d940d2c89b7f0.png" width="500">

# Sniffing with parameter “-i”

Start the Snort instance in verbose mode (-v) and use the interface (-i) “eth0”; sudo snort -v-i eth0

# Sniffing with parameter “-v”

Start the Snort instance in verbose mode (-v); sudo snort -v

# Sniffing with parameter “-d”

Start the Snort instance in dumping packet data mode (-d); sudo snort -d

# Sniffing with parameter “-de”

Start the Snort instance in dump (-d) and link-layer header grabbing (-e) mode; snort -d -e

# Sniffing with parameter “-x”

Start the Snort instance in full packet dump mode (-X); sudo snort -X


# Running Snort in Logger Mode
You can use Snort as a sniffer and log the sniffed packets via logger mode. You only need to use the packet logger mode parameters, and Snort does the rest to accomplish this.

<img src="https://i.gyazo.com/d9a4c2d3a3a855f5a1d70d17a2558496.png" width="500">

Logfile Ownership  Remember, whoever creates a file becomes the owner of said file, to use snort you must escalate privileges using "sudo" <br>
You can also elevate the session privileges and switch to the superuser account to examine the generated log files by using the command "sudo su"

# Logging with parameter “-l”

First, start the Snort instance in packet logger mode; sudo snort -dev -l

# Logging with parameter “-K ASCII”

Start the Snort instance in packet logger mode; sudo snort -dev -K ASCII

# Reading generated logs with parameter “-r”

Start the Snort instance in packet reader mode; sudo snort -r

“-r” parameter also allows users to filter the binary log files. You can filter the processed log to see specific packets with the “-r” parameter and Berkeley Packet Filters (BPF).


























