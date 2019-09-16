# open-switching-info

Information to make sense of the state of open switching/routing

## switch OSes/stacks

 name                                                                                           | active development | bare-metal | routing | state         | hardware abstraction | license                    | notes
 -----------------------------------------------------------------------------------------------|--------------------|------------|---------|---------------|----------------------|----------------------------|------
 [ACS](https://azure.microsoft.com/en-us/blog/microsoft-showcases-the-azure-cloud-switch-acs/)  | no?                | yes?       |         | SONiC         | SAI                  |                            | announced in 2015, not sure if this is an actual product or just the predecessor to SONiC?
 [cumulus](https://cumulusnetworks.com/)                                                        | yes                | yes        | FRR     | Linux kernel  | switchd              |                            | 
 [picOS](https://www.pica8.com/)                                                                | yes                | yes        |         | OVSDB?        | openflow             |                            | 
 [ONL](https://opennetlinux.org/)                                                               | yes                | yes        |         |               | openflow             |                            | 
 [switch light](https://www.bigswitch.com/solutions/technology/switch-light)                    |                    |Switch Light OS |     | indigo        | ivs/openflow?        |                            |                    
 [stratum](https://www.opennetworking.org/stratum/)                                             | no public release  | yes?       |         |               | P4Runtime            |                            | not yet available (09/2019)
 [OpenSwitch OPS](https://bm-switch.com/index.php/blog/whitebox_basics_ops/)                    | no                 | yes        |         | OVSDB         | openNSL              |                            | deprecated?
 [OpenSwitch OPX](https://www.openswitch.net/)                                                  | yes                | yes        |         | Linux/CPS adapter | SAI              | APLv2, various?            | 
 [Noviware]()                                                                                   |                    | yes        |         | proprietary?  | P4/openflow          | proprietary?               | 
 [Vyatta]()/VyOS                                                                                |                    | yes        | quagga  | Linux         | Linux (software)     | various open-source        | runs on x86 hardware for software forwarding
 [snaproute](https://www.snaproute.com/)                                                        |                    | CN-NOS     |         | FlexSwitch    | asicd                |                            | 
 [FBOSS]()                                                                                      |                    |            | FBOSS?  |               | SAI (was OpenNSL)    | BSD-style                  | all-in-one?
 [ONOS](https://onosproject.org/)                                                               |                    |            |         |               | openflow/netconf/openconf/...   | APLv2           | [wiki](https://wiki.onosproject.org)
 [openvswitch](https://www.openvswitch.org/)                                                    |                    |            | N/A     | OVSDB         | software?            | APLv2                      | software forwarding
 [ZebOS](https://www.ipinfusion.com/products/zebos/)                                            | yes                |            |         | ZebM/ZebOS-XP | ZebIC                | proprietary                | 
 .                                                                                              |                    |            |         |               |                      |                            | 



## networking controllers

I haven't decided where these fit yet:

 * Ryu (openflow controller, written in python)
 * openstack neutron (datacenter virtualization orchestration?)
 * open daylight


## routing daemons

 name                                             | license                 | notes                              
--------------------------------------------------|-------------------------|------------------------------------
 [BIRD](https://bird.network.cz/)                 | GPL                     | common in route reflectors
 [FRR](https://frrouting.org/)                    |                         | "Free Range Routing" (fork of Quagga)
 [Quagga](http://www.quagga.net/)                 |                         | fork of Zebra
 [zebra]()                                        |                         | (old, unmaintained)
 [FBOSS](https://github.com/facebook/fboss)       |                         | 
 [XORP](http://www.xorp.org/)                     |                         | 
 [GoBGP](https://github.com/osrg/gobgp)           | APL2.0                  | 
 [openBGPD/openOSPFD](http://www.openbgpd.org/)   | BSD                     | 
 [exaBGP](https://github.com/Exa-Networks/exabgp) | BSD-style               | used for integration rather than forwarding
 .                                                |                         | 


## State-handling

 name                                                                     | license                     | notes                              
 -------------------------------------------------------------------------|-----------------------------|------------------------------------
 [SONiC](https://azure.github.io/SONiC/)                                  |                             | 
 Linux Kernel                                                             |                             | 
 [OVSDB]()                                                                | APLv2                       | There are a lot of proprietary vendor implementations, part of openvswitch
 [FlexSwitch]()                                                           |                             | 
 [IVS (indigo)](http://www.projectfloodlight.org/indigo-virtual-switch/)  | EPLv1 or proprietary        | 
 .                                                                        |                             | 


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
 [indigo](http://www.projectfloodlight.org/indigo/)  | EPLv1 or proprietary       |                    | abstraction layer on top of openflow
 .              |                               |                    |

