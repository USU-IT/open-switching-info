# open-switching-info

Information to make sense of the state of open switching/routing

## switch OSes/stacks

 name            | bare-metal | routing | state         | hardware abstraction | license            | notes                                            | more info
 ----------------|------------|---------|---------------|--------------|----------------------------|--------------------------------------------------|----------
 ACS             | yes?       |         | SONiC         | SAI          |                            |                                                  | https://azure.microsoft.com/en-us/blog/microsoft-showcases-the-azure-cloud-switch-acs/
 cumulus         | yes        | FRR     | Linux kernel  | switchd      |                            |                                                  | https://cumulusnetworks.com/
 picOS           | yes        |         | OVSDB?        | openflow     |                            |                                                  | https://www.pica8.com/
 ONL             | yes        |         |               | openflow     |                            |                                                  | https://opennetlinux.org/
 switch light    |Switch Light OS |     |               | openflow     |                            | openflow controller                              | https://www.bigswitch.com/solutions/technology/switch-light
 stratum         | yes?       |         |               | P4Runtime    |                            | not yet available (09/2019)                      | 
 OpenSwitch OPS  | yes        |         | OVSDB         | openNSL      |                            | deprecated?                                      |
 OpenSwitch OPX  | yes        |         | Linux/CPS adapter | SAI      |                            |                                                  | https://www.openswitch.net/
 Noviware        | yes        |         | proprietary?  | P4/openflow  | proprietary?               |                                                  | 
 Vyatta/VyOS     | yes        | quagga  | Linux         | Linux (software) | various open-source    | runs on x86 hardware for software forwarding     | 
 snaproute       | CN-NOS     |         | FlexSwitch    | asicd        |                            |                                                  | https://www.snaproute.com/
 FBOSS           |            | FBOSS?  |               | SAI (was OpenNSL) |                       | all-in-one?                                      | 
 ONOS            |            |         |               | openflow/netconf/openconf/...   |         |                                                  | https://onosproject.org/ https://wiki.onosproject.org         
 openvswitch     |            | N/A     | OVSDB         | software?    |                            | software forwarding                              | https://www.openvswitch.org/
 .               |            |         |               |              |                            |                                                  |          



## networking controllers

I haven't decided where these fit yet:

 * Ryu (openflow controller, written in python)
 * openstack neutron (datacenter virtualization orchestration?)


## routing daemons

 name                                             | license                 | notes                              
--------------------------------------------------|-------------------------|------------------------------------
 [BIRD](https://bird.network.cz/)                 | GPL                     | common in route reflectors
 [FRR](https://frrouting.org/)                    |                         | "Free Range Routing" (fork of Quagga)
 [Quagga](http://www.quagga.net/)                 |                         | fork of Zebra
 zebra                                            |                         | (old, unmaintained)
 [FBOSS](https://github.com/facebook/fboss)       |                         | 
 [XORP](http://www.xorp.org/)                     |                         | 
 [GoBGP](https://github.com/osrg/gobgp)           | APL2.0                  | 
 [openBGPD/openOSPFD](http://www.openbgpd.org/)   | BSD                     | 
 [exaBGP](https://github.com/Exa-Networks/exabgp) | BSD-style               | used for integration rather than forwarding
 .                                                |                         | 


## State-handling

 name           | license                     | notes                              
 ---------------|-----------------------------|------------------------------------
 SONiC          |                             | 
 Linux Kernel   |                             | 
 OVSDB          |                             | 
 FlexSwitch     |                             | 
 .              |                             | 


## Hardware abstraction (forwarding)

 name           | license                       | supported hardware | notes                             
 ---------------|-------------------------------|--------------------|-----------------------------------
 [SAI](https://github.com/opencomputeproject/SAI)            | OWFa1.0                       |                    |
 [switchdev](https://www.kernel.org/doc/Documentation/networking/switchdev.txt)      | GPLv2                         |                    |
 [openflow]()       | implementation-specific       |                    | IP-based API specification, not an implementation
 [P4Runtime](https://p4.org/p4-runtime)      | implementation-specific?      |                    | match-action programming language
 [openNSL](https://github.com/Broadcom-Switch/OpenNSL)        | APL2.0/Proprietary            | Broadcom           |
 [asicd](https://github.com/FlexSNR/asicd)          | APL2.0?                       |                    |
 linux/software | GPLv2                         |                    |
 .              |                               |                    |

