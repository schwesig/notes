Here are the current available MIBs we use: 
- [https://github.com/OCP-on-NERC/snmp-config-generator/tree/main/mibs](https://github.com/OCP-on-NERC/snmp-config-generator/tree/main/mibs)

Here are the (some) sources of the mibs:   
- [https://github.com/cisco/cisco-mibs](https://github.com/cisco/cisco-mibs)
- [https://github.com/librenms/librenms](https://github.com/librenms/librenms)
- [https://github.com/kcsinclair/mibs.git](https://github.com/kcsinclair/mibs.git)
---
## Part 1 Power, CPU, Fans, Environment
| Metric | Explanation | Unit | Additive |
|:---|:---|:---|:---|
| network_switch_cefcFRUActualInputCurrent | Actual input current for a Field Replaceable Unit (FRU) | Ampere | No |
| network_switch_cefcFRUActualOutputCurrent | Actual output current for a Field Replaceable Unit (FRU) | Ampere | No |
| network_switch_cefcFRUCurrent | Measured current for FRU device | Ampere | No |
| network_switch_cefcFRUPowerAdminStatus | Administrative power status (configured) of FRU | Status (enum) | No |
| network_switch_cefcFRUPowerOperStatus | Operational power status (actual) of FRU | Status (enum) | No |
| network_switch_cefcFanSpeed | Fan speed in RPM | RPM | No |
| network_switch_cefcFanSpeedPercent | Fan speed relative to maximum (percentage) | Percent | No |
| network_switch_cefcFanTrayDirection | Airflow direction of fan tray | Direction (enum) | No |
| network_switch_cefcFanTrayOperStatus | Operational status of fan tray | Status (enum) | No |
| network_switch_cefcPowerRedundancyMode | Configured power redundancy mode | Mode (enum) | No |
| network_switch_cefcPowerRedundancyOperMode | Operational power redundancy mode | Mode (enum) | No |
| network_switch_cefcPowerUnits | Number of installed power units | Count | No |
| network_switch_cefcTotalAvailableCurrent | Total available current capacity | Ampere | No |
| network_switch_cefcTotalDrawnCurrent | Total drawn current by all modules | Ampere | No |
| network_switch_cpmCPUTotal1minRev | CPU utilization averaged over 1 minute | Percent | No |
| network_switch_cpmCPUTotal5minRev | CPU utilization averaged over 5 minutes | Percent | No |
| network_switch_cpmProcessTimeCreated | Time when CPU process started | Timestamp | No |
| network_switch_dellNetCpuFlashUsageUtil | CPU flash storage utilization | Percent | No |
| network_switch_dellNetCpuUtil1Min | CPU usage averaged over 1 minute | Percent | No |
| network_switch_dellNetCpuUtil5Min | CPU usage averaged over 5 minutes | Percent | No |
| network_switch_dellNetCpuUtil5Sec | CPU usage averaged over 5 seconds | Percent | No |
| network_switch_dellNetCpuUtilMemUsage | CPU memory usage | Percent | No |
| network_switch_dellNetPowerSupplyExpressServiceCode | Dell Express Service Code of power supply | String | No |
| network_switch_dellNetPowerSupplyOperStatus | Operational status of Dell power supply | Status (enum) | No |
| network_switch_dellNetPowerSupplyPPIDRevision | PPID revision of power supply | String | No |
| network_switch_dellNetPowerSupplyPiecePartID | Piece Part ID of power supply | String | No |
| network_switch_dellNetPowerSupplyServiceTag | Dell Service Tag of power supply | String | No |
| network_switch_dellNetPowerSupplyType | Type of Dell power supply | Type (enum) | No |
| network_switch_dellNetPowerSupplyUsage | Power consumed by power supply | Watts | No |
| network_switch_dellNetSwModuleBootFlashImgVersion | Boot flash image version of module | Version | No |
| network_switch_dellNetSwModuleBootSelectorImgVersion | Boot selector image version | Version | No |
| network_switch_dellNetSwModuleCurrentBootImage | Currently used boot image | String | No |
| network_switch_dellNetSwModuleInPartitionAImgVers | Image version in Partition A | Version | No |
| network_switch_dellNetSwModuleInPartitionBImgVers | Image version in Partition B | Version | No |
| network_switch_dellNetSwModuleNextRebootImage | Boot image set for next reboot | String | No |
| network_switch_dellNetSwModuleRuntimeImgDate | Build date of running image | Date | No |
| network_switch_dellNetSwModuleRuntimeImgVersion | Running firmware/software version | Version | No |
| network_switch_envMonFanSpeed | Environmental monitoring: fan speed | RPM | No |
| network_switch_envMonFanState | Environmental monitoring: fan state | Status (enum) | No |
| network_switch_envMonSupplySource | Power source for environmental supply | Source (enum) | No |
| network_switch_envMonSupplyState | Operational state of environmental supply | Status (enum) | No |
| network_switch_envMonSupplyStatusDescr | Description of supply state | String | No |
| network_switch_envMonSupplyStatusIndex | Index for supply state entry | Integer | No |
## Part 2 Packets, Errors, Bandwidth, Status, ...
| Metric | Explanation | Unit | Additive |
|:---|:---|:---|:---|
| network_switch_ifAdminStatus | Administrative status of the interface (up/down) | Status (enum) | No |
| network_switch_ifConnectorPresent | Indicates if a physical connector is present | Boolean | No |
| network_switch_ifCounterDiscontinuityTime | Time of last counter reset/discontinuity | Timestamp | No |
| network_switch_ifHCInBroadcastPkts | High-capacity count of incoming broadcast packets | Packets | Yes |
| network_switch_ifHCInMulticastPkts | High-capacity count of incoming multicast packets | Packets | Yes |
| network_switch_ifHCInOctets | High-capacity count of incoming octets (bytes) | Bytes | Yes |
| network_switch_ifHCInUcastPkts | High-capacity count of incoming unicast packets | Packets | Yes |
| network_switch_ifHCOutBroadcastPkts | High-capacity count of outgoing broadcast packets | Packets | Yes |
| network_switch_ifHCOutMulticastPkts | High-capacity count of outgoing multicast packets | Packets | Yes |
| network_switch_ifHCOutOctets | High-capacity count of outgoing octets (bytes) | Bytes | Yes |
| network_switch_ifHCOutUcastPkts | High-capacity count of outgoing unicast packets | Packets | Yes |
| network_switch_ifHighSpeed | Speed of the interface in Mbps | Mbps | No |
| network_switch_ifInBroadcastPkts | Incoming broadcast packets | Packets | Yes |
| network_switch_ifInDiscards | Incoming packets discarded | Packets | Yes |
| network_switch_ifInErrors | Incoming packets with errors | Packets | Yes |
| network_switch_ifInMulticastPkts | Incoming multicast packets | Packets | Yes |
| network_switch_ifInNUcastPkts | Incoming non-unicast (multicast + broadcast) packets | Packets | Yes |
| network_switch_ifInOctets | Incoming octets (bytes) | Bytes | Yes |
| network_switch_ifInUcastPkts | Incoming unicast packets | Packets | Yes |
| network_switch_ifInUnknownProtos | Incoming packets with unknown protocols | Packets | Yes |
| network_switch_ifIndex | Unique index for the interface | Integer | No |
| network_switch_ifLastChange | Last time interface changed operational status | Timestamp | No |
| network_switch_ifLinkUpDownTrapEnable | Whether link up/down traps are enabled | Boolean | No |
| network_switch_ifMtu | Maximum transmission unit size | Bytes | No |
| network_switch_ifOperStatus | Operational status of the interface (up/down/testing) | Status (enum) | No |
| network_switch_ifOutBroadcastPkts | Outgoing broadcast packets | Packets | Yes |
| network_switch_ifOutDiscards | Outgoing packets discarded | Packets | Yes |
| network_switch_ifOutErrors | Outgoing packets with errors | Packets | Yes |
| network_switch_ifOutMulticastPkts | Outgoing multicast packets | Packets | Yes |
| network_switch_ifOutNUcastPkts | Outgoing non-unicast (multicast + broadcast) packets | Packets | Yes |
| network_switch_ifOutOctets | Outgoing octets (bytes) | Bytes | Yes |
| network_switch_ifOutQLen | Output queue length (pending packets) | Packets | No |
| network_switch_ifOutUcastPkts | Outgoing unicast packets | Packets | Yes |
| network_switch_ifPhysAddress | Physical MAC address of the interface | MAC Address | No |
| network_switch_ifPromiscuousMode | Whether interface is in promiscuous mode | Boolean | No |
| network_switch_ifSpecific | Specific interface type (vendor specific) | Object ID | No |
| network_switch_ifSpeed | Current interface speed | bps | No |
| network_switch_ifType_info | Interface type (e.g., Ethernet, Loopback) | Interface Type (enum) | No |

## Part 3 IPv4/IPv6 Metrics, SNMP Metrics, ...
| Metric | Explanation | Unit | Additive |
|:---|:---|:---|:---|
| network_switch_ipv4InterfaceEnableStatus | Whether IPv4 is enabled on interface | Boolean | No |
| network_switch_ipv4InterfaceReasmMaxSize | Maximum size of reassembled IPv4 packet | Bytes | No |
| network_switch_ipv4InterfaceRetransmitTime | IPv4 retransmit timeout value | Milliseconds | No |
| network_switch_ipv6TcpConnIfIndex | Interface index for IPv6 TCP connection | Integer | No |
| network_switch_ipv6TcpConnState | State of IPv6 TCP connection | TCP State (enum) | No |
| network_switch_snmpEnableAuthenTraps | Whether SNMP authentication traps are enabled | Boolean | No |
| network_switch_snmpInASNParseErrs | Incoming SNMP packets with ASN.1 parse errors | Packets | Yes |
| network_switch_snmpInBadCommunityNames | Incoming SNMP packets with invalid community names | Packets | Yes |
| network_switch_snmpInBadCommunityUses | Incoming SNMP packets using wrong community name | Packets | Yes |
| network_switch_snmpInBadValues | Incoming SNMP packets with bad values | Packets | Yes |
| network_switch_snmpInBadVersions | Incoming SNMP packets with unsupported versions | Packets | Yes |
| network_switch_snmpInGenErrs | Incoming SNMP packets with general errors | Packets | Yes |
| network_switch_snmpInGetNexts | Incoming SNMP Get-Next requests | Requests | Yes |
| network_switch_snmpInGetRequests | Incoming SNMP Get requests | Requests | Yes |
| network_switch_snmpInGetResponses | Incoming SNMP Get responses | Responses | Yes |
| network_switch_snmpInNoSuchNames | SNMP errors: no such name | Errors | Yes |
| network_switch_snmpInPkts | Total incoming SNMP packets | Packets | Yes |
| network_switch_snmpInReadOnlys | Incoming SNMP write attempts to read-only variables | Packets | Yes |
| network_switch_snmpInSetRequests | Incoming SNMP Set requests | Requests | Yes |
| network_switch_snmpInTooBigs | SNMP errors: too big response | Errors | Yes |
| network_switch_snmpInTotalReqVars | Total variables requested in incoming SNMP packets | Variables | Yes |
| network_switch_snmpInTotalSetVars | Total variables set in incoming SNMP packets | Variables | Yes |
| network_switch_snmpInTraps | Incoming SNMP traps received | Traps | Yes |
| network_switch_snmpOutBadValues | Outgoing SNMP responses with bad values | Packets | Yes |
| network_switch_snmpOutGenErrs | Outgoing SNMP responses with general errors | Packets | Yes |
| network_switch_snmpOutGetNexts | Outgoing SNMP Get-Next requests | Requests | Yes |
| network_switch_snmpOutGetRequests | Outgoing SNMP Get requests | Requests | Yes |
| network_switch_snmpOutGetResponses | Outgoing SNMP Get responses | Responses | Yes |
| network_switch_snmpOutNoSuchNames | SNMP responses: no such name | Errors | Yes |
| network_switch_snmpOutPkts | Total outgoing SNMP packets | Packets | Yes |
| network_switch_snmpOutSetRequests | Outgoing SNMP Set requests | Requests | Yes |
| network_switch_snmpOutTooBigs | SNMP responses: too big | Errors | Yes |
| network_switch_snmpOutTraps | Outgoing SNMP traps | Traps | Yes |
| network_switch_snmpProxyDrops | Dropped SNMP proxy packets | Packets | Yes |
| network_switch_snmpSilentDrops | Dropped SNMP packets without notification | Packets | Yes |
| network_switch_snmp_scrape_duration_seconds | Duration of SNMP scrape operation | Seconds | No |
| network_switch_snmp_scrape_packets_retried | Number of retried packets during SNMP scrape | Packets | Yes |
| network_switch_snmp_scrape_packets_sent | Total packets sent during SNMP scrape | Packets | Yes |
| network_switch_snmp_scrape_pdus_returned | PDUs returned during SNMP scrape | PDUs | Yes |
| network_switch_snmp_scrape_walk_duration_seconds | Duration of SNMP walk operation | Seconds | No |

## Part 4 System Information, TCP/UDP Metrics
| Metric | Explanation | Unit | Additive |
|:---|:---|:---|:---|
| network_switch_sysContact | System administrator contact information | String | No |
| network_switch_sysDescr | Full system description (hardware, OS) | String | No |
| network_switch_sysLocation | Physical location of the device | String | No |
| network_switch_sysName | System name (hostname) | String | No |
| network_switch_sysORDescr | Description of supported MIB modules | String | No |
| network_switch_sysORID | OID of supported MIB module | Object ID | No |
| network_switch_sysORLastChange | Last change time of MIB module list | Timestamp | No |
| network_switch_sysORUpTime | Time since last MIB list change | Ticks | No |
| network_switch_sysObjectID | Unique identifier for the device type | Object ID | No |
| network_switch_sysServices | Services supported (Layer 2, Layer 3 etc.) | Bitmask | No |
| network_switch_sysUpTime | Time since last reboot | Ticks | No |
| network_switch_tcpActiveOpens | TCP connections actively opened | Connections | Yes |
| network_switch_tcpAttemptFails | TCP connection attempts that failed | Failures | Yes |
| network_switch_tcpConnLocalAddress | Local address of a TCP connection | IP Address | No |
| network_switch_tcpConnLocalPort | Local port of a TCP connection | Port | No |
| network_switch_tcpConnRemAddress | Remote address of a TCP connection | IP Address | No |
| network_switch_tcpConnRemPort | Remote port of a TCP connection | Port | No |
| network_switch_tcpConnState | State of a TCP connection | TCP State (enum) | No |
| network_switch_tcpConnectionProcess | Process associated with TCP connection | Process ID | No |
| network_switch_tcpConnectionState | Current TCP connection state | TCP State (enum) | No |
| network_switch_tcpCurrEstab | Current number of established TCP connections | Connections | No |
| network_switch_tcpEstabResets | TCP connections reset after established | Resets | Yes |
| network_switch_tcpHCInSegs | Incoming TCP segments (high capacity) | Segments | Yes |
| network_switch_tcpHCOutSegs | Outgoing TCP segments (high capacity) | Segments | Yes |
| network_switch_tcpInErrs | Incoming TCP segments with errors | Errors | Yes |
| network_switch_tcpInSegs | Incoming TCP segments | Segments | Yes |
| network_switch_tcpListenerProcess | Process handling TCP listener socket | Process ID | No |
| network_switch_tcpMaxConn | Maximum TCP connections supported | Connections | No |
| network_switch_tcpOutRsts | TCP reset segments sent | Resets | Yes |
| network_switch_tcpOutSegs | Outgoing TCP segments | Segments | Yes |
| network_switch_tcpPassiveOpens | TCP connections passively accepted (listened) | Connections | Yes |
| network_switch_tcpRetransSegs | Retransmitted TCP segments | Segments | Yes |
| network_switch_tcpRtoAlgorithm | TCP retransmission timeout algorithm used | Algorithm (enum) | No |
| network_switch_tcpRtoMax | Maximum retransmission timeout | Milliseconds | No |
| network_switch_tcpRtoMin | Minimum retransmission timeout | Milliseconds | No |
| network_switch_udpEndpointProcess | Process handling UDP endpoint | Process ID | No |
| network_switch_udpHCInDatagrams | Incoming UDP datagrams (high capacity) | Datagrams | Yes |
| network_switch_udpHCOutDatagrams | Outgoing UDP datagrams (high capacity) | Datagrams | Yes |
| network_switch_udpInDatagrams | Incoming UDP datagrams | Datagrams | Yes |
| network_switch_udpInErrors | Incoming UDP errors (e.g., checksum errors) | Errors | Yes |
| network_switch_udpLocalAddress | Local address of UDP endpoint | IP Address | No |
| network_switch_udpLocalPort | Local port of UDP endpoint | Port | No |
| network_switch_udpNoPorts | UDP packets dropped because no application was listening | Datagrams | Yes |
| network_switch_udpOutDatagrams | Outgoing UDP datagrams | Datagrams | Yes |
