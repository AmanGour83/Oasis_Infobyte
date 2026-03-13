Basic Firewall Configuration using UFW

Objective

The objective of this task is to configure a basic firewall on a Linux system using Uncomplicated Firewall (UFW). The firewall is configured to allow secure remote access via SSH while blocking HTTP traffic to demonstrate basic firewall rule management.


---

Environment

Operating System:

Kali Linux


Firewall Tool:

Uncomplicated Firewall (UFW)



---

Installing UFW

First, the firewall package was installed (or verified if already installed).

sudo apt install ufw

The installed version was verified using:

ufw version


---

Enabling the Firewall

The firewall was enabled using the following command:

sudo ufw enable

This activates the firewall and ensures it starts automatically during system startup.


---

Firewall Rules Configuration

Two firewall rules were configured:

Allow SSH Access

SSH traffic was allowed to enable remote administration.

sudo ufw allow ssh

This allows incoming traffic on port 22.


---

Deny HTTP Traffic

HTTP traffic was blocked to prevent web access.

sudo ufw deny http

This blocks incoming traffic on port 80.


---

Checking Firewall Status

The configured firewall rules were verified using:

sudo ufw status

Output Summary

Port	Protocol	Action	Purpose

22	TCP	ALLOW	Enables secure remote login via SSH
80	TCP	DENY	Blocks HTTP web traffic


IPv6 rules were also automatically applied by UFW.


---

Screenshot

The screenshot included in this repository shows the firewall configuration process and the final firewall status confirming:

SSH traffic is allowed

HTTP traffic is blocked

Firewall status is active



---

Conclusion

This task demonstrates the basic configuration of a Linux firewall using Uncomplicated Firewall. By allowing only required services (such as SSH) and blocking unnecessary ones (such as HTTP), administrators can reduce the attack surface and improve system security.


 