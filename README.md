**Summary of how firewal filters traffic**

I used the `iptables` utility in Kali Linux for firewall management.

1.  **Initial State:** The firewall rules were listed using `sudo iptables -L` to understand the existing configuration.
2.  **Blocking Telnet (Port 23):** The command `sudo iptables -A INPUT -p tcp --dport 23 -j DROP` was executed to block all incoming traffic on Port 23.
3.  **Testing the Rule:** The test command `telnet 127.0.0.1 23` resulted in a **"Connection timed out"** message, verifying that the `DROP` rule was effective.
4.  **Allowing SSH (Port 22):** The rule `sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT` was added to ensure continued remote access.
5.  **Restoration:** The test block rule was deleted using `sudo iptables -D INPUT -p tcp --dport 23 -j DROP` to return the firewall to its original configuration.
