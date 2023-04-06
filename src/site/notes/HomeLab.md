---
{"dg-publish":true,"permalink":"/home-lab/","created":"2023-03-19T19:41:40.835-04:00","updated":"2023-04-06T15:46:04.742-04:00"}
---

While I have certainly had plenty of servers and devices at home over the years, I had taken a few years off from noodling at home and focused on consumer hardware from Apple, Eero, etc.  Playing with Linux was relegated to VMware or Parallels virtual machines on my Macs, and I hosted my websites on Linux hosts at DigitalOcean and later AWS Lightsail.  What little Windows I have played with has been virtualized on my Macs, as well.

Recently, I decided to freshen my technical skills and start focusing more on my professional development.  So I decided to build a HomeLab to use as a learning sandbox as well as stand up services such as Pi-Hole for household use.

I'm adding hardware to my HomeLab opportunistically..  basically grabbing freebie's from friends, buying used devices online, and occasionally splurging for a new component here and there.  So I expect my configuration will evolve over time as I am able to acquire better and interesting things.  My HomeLab is located in my home office, so I plan to try to buy only relatively quiet devices or devices where I can swap in quiet fans.  With that in mind, I don't plan on adding any enterprise-grade servers.

[[OptiPlex Micro repair\|OptiPlex Micro repair]]

Things are in flux as I've procured some new hardware but I haven't introduced it to the HomeLab yet. Stay tuned for updates.

#### HomeLab Hardware as of 2023-03-19

- 27" Enclosed rack
- 1U Power distribution with 8 independently switched outlets
- Old monitor, keyboard, and mouse
- 1U 24-port keystone patch panel with CAT6 and HDMI keystones
- Two 8-port simple managed gibabit switches (One TP-Link, one NetGear)
- ISP managed router with 4 available gigabit ports
- Eero mesh WiFi
- Two ancient x86 hosts
- One more recent Dell Optiplex Micro x86 host (I love these!)
- One Synology Storage Server (NAS)
- One Raspberry Pi 4B w/ 4GB RAM
- One Raspberry Pi Pico
- Three Raspberry Pi Pico W's

#### HomeLab Software as of 2023-03-19

- All three x86 boxes are running Proxmox VE
- PFsense is my firewall/router running virtualized on one Proxmox host
- The Raspberry Pi 4B is running Pi-Hole
- The Pico and one of the Pico W's are both set up as temperature sensors for the rack.  The non-WiFi Pico shows the temperature on 7-segment LED displays.  The WiFi Pico serves the temperature via port 80.
- A Ubunu Linux instance on one of the Proxmox servers polls and logs the temperature from the Pico W every 5 minutes.
- I had k3s and Rancher up and running for a bit as VM's on the proxmox systems, but I tore it all down to start over.

#### HomeLab Network as of 2023-03-19
- WAN network, DHCP served by ISP router
- LAN network, DHCP served by PFsense router (production/household)
- LAB network, DHCP served by PFsense router (scratch space)
