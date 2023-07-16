<img src="https://i.gyazo.com/ea8218ce8d986ee5293cc13971912e91.png" width="600"> <br>
# Snort Basic setup

When initiating Snort for the first time, it is essential to validate the configuration file. The '-t' flag is utilized to test the configuration's validity, while the '-c' flag creates a new configuration file.
-t is used to test configuration, and -c makes a new configuration file

<img src="https://i.gyazo.com/829b48746afe86d8cc03922fa279bfa4.png" width="400">

# Sniffer mode

Similar to tcpdump, Snort offers a range of flags that allow users to examine diverse packet data as it gets ingested. The table below provides an explanation of the sniffer mode parameters

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
"Snort can be utilized as a sniffer, enabling the logging of captured packets through the logger mode. By simply employing the packet logger mode parameters, Snort takes care of the necessary steps to accomplish this seamlessly.
<img src="https://i.gyazo.com/d9a4c2d3a3a855f5a1d70d17a2558496.png" width="500">

It's crucial to keep in mind that the owner of a file is determined by the user who creates it. To utilize Snort, it is necessary to elevate privileges using 'sudo' in order to access the required resources. Alternatively, you can elevate session privileges and switch to the superuser account using the command 'sudo su' to examine the generated log files.

# Logging with parameter “-l”

First, start the Snort instance in packet logger mode; sudo snort -dev -l

# Logging with parameter “-K ASCII”

Start the Snort instance in packet logger mode; sudo snort -dev -K ASCII

# Reading generated logs with parameter “-r”

Start the Snort instance in packet reader mode; sudo snort -r

The '-r' parameter additionally enables users to apply filters on the binary log files. By combining the '-r' parameter with Berkeley Packet Filters (BPF), it becomes possible to narrow down the processed log and focus on specific packets of interest."

























