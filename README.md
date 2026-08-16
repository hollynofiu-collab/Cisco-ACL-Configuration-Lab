# Cisco-ACL-Configuration-Lab
Cisco Packet Tracer lab demonstrating ACL configuration, traffic filtering, inter-VLAN access control, and network security policy enforcement using Cisco IOS.

This project documents the configuration and verification of Access Control Lists (ACLs) on a Cisco router using Cisco Packet Tracer.
The ACL was implemented within a Router-on-a-Stick network environment to control traffic between different VLANs and demonstrate how network access policies can be enforced at the routing layer.
The primary focus of this project is ACL configuration, traffic filtering, and verification.

## Objectives

-Configure an ACL on a cisco router

-Control traffic between segments

-Apply access-control rules to the appropriate router interface.

-Verify the Acl Configuration.

-Test permitted and denied traffic

-Understand how ACLs can be used as a network security control.

## Network Context.

The ACL was configured on the router within a segmented VLAN environment.
The Router-on-a-Stick configuration provides inter-VLAN routing, while the ACL introduces traffic-control policies between the network segments.

## Configuration

![Configuration](https://github.com/hollynofiu-collab/Cisco-ACL-Configuration-Lab/blob/main/Configuration.txt)

## Testing/Verification.

The ACL was tested from PC3 to verify that the configured traffic policy
was being enforced.

### Test 1 — Permitted Traffic

PC3 successfully communicated with `192.168.30.22`.

- Packets sent: 4
- Packets received: 4
- Packet loss: 0%

This confirms that traffic not matching the deny rule was permitted.

### Test 2 — Denied Traffic

PC3 attempted to communicate with `192.168.40.3`.

- Packets sent: 4
- Packets received: 0
- Packet loss: 100%

The traffic was blocked because the source network
`192.168.20.0/24` is denied access to the destination network
`192.168.40.0/24` by ACL 100.

![ACL Traffic Testing](screenshots/acl-traffic-testing.png)


