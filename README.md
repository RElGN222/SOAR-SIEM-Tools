# SOAR-SIEM-Tools

Basic Network Scan in Nessus, without credentials

<img src="https://i.gyazo.com/3484298ba17cb1ec91552e6b758f9175.png" width="600">

As we can see, SMB signing is not required. An attacker could exploit this vulnerability by launching a man-in-the-middle attack, or execute a replay attack against SMB communications.
To mitigate this, Use Group Policy Editor to enable "Digitally Sign Communications (always)" on the network server


Authenticated Scans, with credentials

<img src="https://i.gyazo.com/4641fae825a699e2ed8014869640eae7.png" width="600">

A Credentialed scan gives us MUCH more information about the system. This is because, without credentials, Nessus does not have privileged access to scan things like the file system and registry. Good practice is to use non-credentialed scans to identify outward facing vulnerabilites, while a credentialed scan allows for deeper insight into the security posture of a system

No Credentials <img src="https://i.gyazo.com/b7d00133382880497f25e4955338ba26.png" width="180">  vs  <img src="https://i.gyazo.com/c3e8058937b5043c394a1393a745067c.png" width="150"> Credentials

Luckily, most of our "new" vulnerabilities are fixed by simply updating windows and software. See this in the Remediations Tab

<img src="https://i.gyazo.com/9ff500f674e5379b4fb0ac48f59b4919.png" width="550">

You can also see which threats are considered most important, in the "VPR Top Threats" tab,
<img src="https://i.gyazo.com/c257c7cb320c442604b44f367657a16c.png" width="550">







