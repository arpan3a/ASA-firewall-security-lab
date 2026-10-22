# Troubleshooting Report

## 1. Far-side ASA interface ping

OSPF routes were correct, but a router could not ping the ASA interface on the opposite zone. The ASA does not normally answer traffic that enters one interface and targets a different ASA interface. Testing a host beyond the ASA provided a valid routed-path test.

## 2. ICMP return traffic

Inside-to-DMZ and inside-to-outside pings failed after restrictive ACLs were applied. ICMP inspection was added to the global policy so valid echo replies could be tracked statefully.

## 3. ACL direction

Initial ACL entries described inside-originated flows but were applied inbound on DMZ and OUTSIDE. ASA interface ACLs evaluate traffic where it enters. The policy was rebuilt from the perspective of DMZ-originated traffic.

## 4. DHCP relay ACL order

A broad DMZ-to-inside deny originally appeared before the DHCP relay-response exception. A new ACL was built with the specific DHCP response first, followed by the general deny.

## 5. DMZ gateway ping

The DMZ ACL's implicit deny prevented DMZ servers from pinging their own ASA interface. A narrow ICMP permit to host `172.16.10.1` enabled gateway diagnostics without granting access to the inside LAN.
