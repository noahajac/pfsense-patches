# pfSense Patches

Custom [pfSense](https://github.com/pfsense/pfsense) patches. These likely don't have use to anyone besides me. Currently for pfSense branch `RELENG_2_5_2`.

* `0001-Custom-Patch-DNS.patch`:
  * Adds [OpenVPN Learn Address](https://github.com/noahajac/openvpn-learn-address) to `/usr/local/bin/openvpn-learn-address`
  * The reverse subnet zone for DHCP dynamic DNS is hardcoded to `10.in-addr.arpa`
  * The DHCP (and DHCPv6) dynamic DNS style is set to `standard`.
  * DHCP (and DHCPv6) dynamic DNS is disabled by default. Is enabled on static mappings.
  * Hardcodes the DHCPv6 dynamic DNS reverse zone.
  * Allows `.` characters in DHCP (and DHCPv6) static mapping hostnames.
  * Adds shell commands to `/etc/rc.carpbackup` and `/etc/rc.carpmaster` that add and remove additional IPv4/IPv6 addresses when vhid 1 goes into backup and master.
* `0002-Custom-Patch-RADIUS.patch`:
  * Modifies FreeRADIUS configuration to default to Access-Accept to a certain VLAN unless a MAC address match is made. Requires creating a Default entry in users.

pfSense is licensed under [the Apache License v2.0](https://www.apache.org/licenses/LICENSE-2.0).
