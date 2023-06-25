# SOP 1.11: Network Connectivity

<br>

## Purpose:

* This ***Standard Operating Procedure (SOP)*** is to establish standards and guidelines for network connectivity on the Globex Network Infrastructure.

<br>

## Scope:

* This ***SOP*** is applicable to all IT administrators responsible for setting up new and/or maintaining current networks.

<br>

## Responsibilities:

* The IT department will be responsible for maintainence and security for networks and associated accounts, software and hardware.

<br>

## Procedure:

* Check IP Addresses [guide](https://itsfoss.com/check-ip-address-ubuntu/)
  * Compare the IP addresses: ("Lab kit pc" and "personal pc")
    * The first three ‘sections’ of the IP address should be the same (e.g. 192.168.1.161 and 192.168.1.12, or 10.0.1.43 and 10.0.1.77)
    * If the first three parts don’t match, then your computers are not on the same network.

* SSH Connectivity
  * Use the APT package manager to confirm that OpenSSH is installed.
  *Create any necessary firewall exceptions to ensure port 22 is open.

  * SSH into your lab computer from your personal computer’s command line interface (Windows Command Line on Windows, or ZSH/Terminal if you are on MacOS). The first time you connect, you’ll need to answer ‘yes’ to some permission questions.

* Remote Desktop Connectivity
  * ***Windows 10:***
    * *Before you make an RDP connection, be sure to log out of your lab computer via the monitor and keyboard attached to it.*
    * Open your RDP client software on your home computer:
      * Windows users will open Remote Desktop Connection, which is an RDP client that comes with Windows.
      * MacOS users will need to download and install [Microsoft Remote Desktop](https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466?mt=12) in order to use the RDP protocol to access Ubuntu remotely.
    * Input the IP address and username of your lab computer into the RDP client on your home computer and establish an RDP connection to your lab computer

<br>

## References:

* [DHCP Reservation](https://homenetworkadmin.com/dhcp-reservation/)

* [Remote Desktop setup](https://linuxconfig.org/ubuntu-20-04-remote-desktop-access-from-windows-10)

* [Ubuntu VNC](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-20-04)

<br>

## Definitions:

* [DHCP Reservation](https://homenetworkadmin.com/dhcp-reservation/)

* [Remote Desktop setup](https://linuxconfig.org/ubuntu-20-04-remote-desktop-access-from-windows-10)

* [Ubuntu VNC](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-20-04)

<br>

## Revision History:

* 06/19/2023 - "SOP_11.md" created by Raphael Chookagian
* 06/21/2023 - Raphael Chookagian
* 06/24/2023 - Ben Hobbs
* 06/25/2023 - Ben Hobbs
