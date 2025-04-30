# Call 2025-04-30
- Chris, Jonathan, Thor
## ToDos
- [ ] sheet to an overview of metrics collected
  - [ ] https://docs.google.com/spreadsheets/d/1WKQnSWOexOiUXfrgQyj4VEW8S6sGl51DZtNJTMdmZNk/edit?usp=sharing
- [ ] how to get no data to zero? (dashboard: yes, export: ?)
- [ ] how can we get data under 10 sec?
  - [ ] irate seems to be 10min and up (in Grafana), can be smaller in OpenShift console, it is maybe a Grafan topic?
- [ ] verify if it is real 5 sec data, and not just a filled/copied from last value
- [ ] dashboard for the metrics we talked about today
  - [ ] DCGM_FI_PROF_PCIE_TX_BYTES
    - [ ] https://docs.nvidia.com/datacenter/dcgm/2.3/dcgm-user-guide/feature-overview.html#profiling
```
PCIe Bandwidth
The rate of data transmitted / received over the PCIe bus,
including both protocol headers and data payloads,
in bytes per second.
The value represents an average over a time interval
and is not an instantaneous value.
The rate is averaged over the time interval. For example,
if 1 GB of data is transferred over 1 second, the rate is 1 GB/s
regardless of the data transferred at a constant rate or in bursts.
The theoretical maximum PCIe Gen3 bandwidth
is 985 MB/s per lane.
```
  - [ ] network_switch_ifMtu
    - [ ] `network_switch_ifMtu{vendor="NVIDIA", ifAlias=~"MOC-R4PCC02U15.*|MOC-R4PCC02U16.*|MOC-R4PCC02U24.*|MOC-R4PCC02U25.*|MOC-R4PCC02U29.*|MOC-R4PCC02U30.*|MOC-R4PCC02U31.*|MOC-R4PCC02U32.*"}`
  - [ ] network_switch_ifHCOutOctets
    - [ ] `network_switch_ifHCOutOctets{vendor="NVIDIA",ifAlias=~"MOC-R4PCC02U15.*|MOC-R4PCC02U16.*|MOC-R4PCC02U24.*|MOC-R4PCC02U25.*|MOC-R4PCC02U29.*|MOC-R4PCC02U30.*|MOC-R4PCC02U31.*|MOC-R4PCC02U32.*"}`
  - [ ] network_switch_ifHCInOctets
- [ ] script and token
- [ ] are all points from jonathan's list included in the query?
  - [ ] `count(network_switch_ifMtu{vendor="NVIDIA", ifAlias=~"MOC-R4PCC02U15.*|MOC-R4PCC02U16.*|MOC-R4PCC02U24.*|MOC-R4PCC02U25.*|MOC-R4PCC02U29.*|MOC-R4PCC02U30.*|MOC-R4PCC02U31.*|MOC-R4PCC02U32.*"}) by (ifDescr)` = 32
  - [ ] `count(network_switch_ifMtu{vendor="NVIDIA", ifAlias=~"MOC-R4PCC02U15.*|MOC-R4PCC02U16.*|MOC-R4PCC02U24.*|MOC-R4PCC02U25.*|MOC-R4PCC02U29.*|MOC-R4PCC02U30.*|MOC-R4PCC02U31.*|MOC-R4PCC02U32.*"}) by (ifAlias, ifDescr)` = 32
  - [ ] `count(network_switch_ifHCOutOctets{vendor="NVIDIA",ifAlias=~"MOC-R4PCC02U15.*|MOC-R4PCC02U16.*|MOC-R4PCC02U24.*|MOC-R4PCC02U25.*|MOC-R4PCC02U29.*|MOC-R4PCC02U30.*|MOC-R4PCC02U31.*|MOC-R4PCC02U32.*"})` = 32
  - [ ] `count(count(network_switch_ifHCOutOctets{vendor="NVIDIA",ifAlias=~"MOC-R4PCC02U15.*|MOC-R4PCC02U16.*|MOC-R4PCC02U24.*|MOC-R4PCC02U25.*|MOC-R4PCC02U29.*|MOC-R4PCC02U30.*|MOC-R4PCC02U31.*|MOC-R4PCC02U32.*"}) by (ifAlias,ifDescr,ifIndex,ifName))` = 32