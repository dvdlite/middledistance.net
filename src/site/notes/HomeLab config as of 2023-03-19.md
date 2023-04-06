---
{"dg-publish":true,"permalink":"/home-lab-config-as-of-2023-03-19/","created":"2023-04-06T16:14:33.400-04:00","updated":"2023-04-06T17:24:20.328-04:00"}
---

#### HomeLab Hardware

- [Sanus CFR2127](https://www.sanus.com/en_um/products/racks/cfr2127/) 27U Enclosed 19" audio/computer rack
- 1U [ADJ PC-100A](https://www.adj.com/pc-100a) Power distribution with 8 independently switched outlets
- IBM [ThinkVision 9417-AB1](http://www.ascendtech.us/ibm-thinkvision-l171-17-lcd-monitor_i_mnibmtvl150lcd3.aspx) VGA monitor (ancient!)
- [Logitech K400+](https://www.logitech.com/en-us/products/keyboards/k400-plus-touchpad-keyboard.920-007119.html) wireless keyboard/mouse combo
- 1U [Cable Matters 24-port keystone patch panel](https://www.cablematters.com/pc-386-162-rack-or-wall-mount-24-port-cat6-cat-6-keystone-patch-panel.aspx) with Qty 21 CAT6 and Qty 2 HDMI keystones
- Two 8-port managed gigabit switches
	- TP-Link [TL-SG108E](https://www.tp-link.com/us/business-networking/easy-smart-switch/tl-sg108e/)
	- NetGear [GS308T](https://www.netgear.com/support/product/gs308t)
- [CyberPower BL1450U](https://www.cyberpowersystems.com/product/ups/battery-backup/bl1450u/) 1450VA Uninterruptable Power Supply
- ISP-managed router with 4 available gigabit ports
- [Eero](https://eero.com) mesh WiFi for the household
- Two ancient x86 nodes donated by a friend: (Thanks, Doug!)
	- [Intel DH77DF Mini-ITX mobo](https://www.intel.com/content/www/us/en/products/sku/59503/intel-desktop-board-dh77df/specifications.html) with an [Intel Core i5-3570K CPU](https://www.intel.com/content/www/us/en/products/sku/65520/intel-core-i53570k-processor-6m-cache-up-to-3-80-ghz/specifications.html), 16GB of RAM, and a 1TB 2.5" SDD
	- [Intel DQ67EP Mini-ITX mobo](https://www.intel.com/content/www/us/en/products/sku/51998/intel-desktop-board-dq67ep/specifications.html) with an [Intel Core i5-2400 CPU]([https://www.intel.com/content/www/us/en/products/sku/52207/intel-core-i52400-processor-6m-cache-up-to-3-40-ghz/specifications.html](https://www.intel.com/content/www/us/en/products/sku/52207/intel-core-i52400-processor-6m-cache-up-to-3-40-ghz/specifications.html)), 16GB of RAM, and a 500GB 2.5" SDD
- Dell OptiPlex Micro 5060 (I love these!):
	- [Intel Q370 mobo](https://ark.intel.com/content/www/us/en/ark/products/133282/intel-q370-chipset.html) with an [Intel Core i5-8500T CPU](https://ark.intel.com/content/www/us/en/ark/products/129941/intel-core-i58500t-processor-9m-cache-up-to-3-50-ghz.html), 8GB RAM, and a 256GB M.2 NVMe SSD
- One [Synology DiskStation DS1019+ 5-Bay NAS](https://global.download.synology.com/download/Document/Hardware/DataSheet/DiskStation/19-year/DS1019+/enu/Synology_DS1019_Plus_Data_Sheet_enu.pdf)
- One [Raspberry Pi 4B w/ 2GB RAM](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/)
- One [Raspberry Pi Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/)
- Three [Raspberry Pi Pico W's](https://www.raspberrypi.com/documentation/microcontrollers/raspberry-pi-pico.html)

#### HomeLab Software

- All three x86 boxes are currently running [Proxmox VE 7.3-4](https://www.proxmox.com/en/proxmox-ve) virtualization engine
- [PFsense 2.6.0-RELEASE](https://www.pfsense.org) is my firewall/router running as a virtualized machine on one Proxmox host
- The Raspberry Pi 4B is running [Pi-Hole](https://pi-hole.net)
- The Pico and one of the Pico W's are both set up as temperature sensors for the rack.  The non-WiFi Pico shows the temperature on 7-segment LED displays.  The WiFi Pico serves the temperature via port 80.
- A [Ubunu Linux](https://ubuntu.com) instance on one of the Proxmox servers polls and logs the temperature from the Pico W every 5 minutes.
- I had [k3s](https://k3s.io) and [Rancher](https://www.rancher.com) up and running for a bit as VM's on the Proxmox systems, but I tore it all down to start over.

#### HomeLab Network
- WAN network, DHCP served by ISP router
- LAN network, DHCP served by PFsense router (production/household)
- LAB network, DHCP served by PFsense router (scratch space)
