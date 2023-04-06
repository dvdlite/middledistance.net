---
{"dg-publish":true,"permalink":"/opti-plex-micro-repair/","created":"2023-04-06T14:52:50.878-04:00","updated":"2023-04-06T15:05:55.248-04:00"}
---

I have been accumulating a few Dell OptiPlex Micro systems to use as worker nodes in my HomeLab.  They are roughly 8"x8"x1.5" and they have room for M.2 SDD storage, 2.5" storage, Intel 6-core i5 processors, and up to 32GB of RAM.  They run Linux very nicely and sip power.

As I receive each system, I have been blowing a minimal Ubuntu Linux image onto them and then stress testing by running s-tui in stress mode.  All but one have passed with flying colors, topping out at around 70-72 degrees Celsius for each core and the CPU package even after hours and hours of tests.  But one node would immediately ramp up to over 80 degrees even as the fan spun at it's maximum.  This would happen within a minute of starting the stress test and then I would quit the test.

I opened up the node and took a look around.  Everything seemed to be in place.  The fan was a bit dusty so I cleaned that up and tried again.  Same results.  After thinking on it a bit, I popped the heat sync off of the CPU and checked it out.  There were two layers of old crusty thermal paste on the CPU and the 2nd layer was maybe half the size of a dime.  So I scrubbed off the old paste and applied a new dose and put everything back together.  Works like a charm now, 70-72 degrees tops after running stress for 24 hours!

Easy fix!


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">



[[01 Colophon\|01 Colophon]] | [[02 License\|02 License]] | [[03 Privacy\|03 Privacy]] | [[04 Contact\|04 Contact]]

</div></div>