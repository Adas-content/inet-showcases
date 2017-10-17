---
layout: page
title: PCAP Recoding
hidden: true
---

## Goals

INET has support for recording pcap traces from simulations. The recording
process produces pcap files that are similar to real world pcap traces,
so one can use the same tools and techniques for analyzing simulated traffic as used on real traffic, such as Wireshark and TCPDump. Knowledge of pcap can be reused in the context of simulations.

This showcase contains example simulation, which generates and records TCP, UDP, and ICMP
traffic, using various protocols like ethernet and 802.11.

INET version: `4.0`<br>
Source files location: <a href="https://github.com/inet-framework/inet-showcases/tree/master/wireless/pcaprecording" target="_blank">`inet/showcases/wireless/pcaprecording`</a>

## The model

In order to record pcap traces in a node, a `PcapRecorder` module needs to be included in the node.
Pcap recorder modules can be easily included in hosts and routers by specifying the `numPcapRecorders` parameter (available in modules that extend `LinkLayerNodeBase`, such as  `StandardHost` and derivatives, and router modules.)

The pcap recorder module records L2 frames sent to and from modules in the same host.
The module records packets containing IPv4 packets (packets not containing IPv4 packets are discarded.) It writes traces in a pcap file, which has to be specified by the `ṗcapFile` parameter.
Specifying this parameter enables packet capture. The pcap recorder module also creates TCPDump-like output on the module log, if the `verbose` parameter is set to `true`.
The pcap file's link layer header type needs to be set with the `pcapNetwork` parameter in order to produce meaningful traces. The most important type codes are the following:

- ethernet: 1
- 802.11: 105
- ppp: 204

- parameters
- operation (signals)

verbose, pcapFile, pcapNetwork, moduleNamePatterns, dumpProtocols?, alwaysFlush?, dumpBadFrames?

Then the config...how to set it

Then, some results. Screenshots of Wireshark, or TCPDump
