# Verification Checklist

- [x] ASA interfaces have the intended names, addresses, and security levels.
- [x] ASA has a static default route to `20.20.20.2`.
- [x] OSPF adjacencies formed with INSIDE and ISP routers.
- [x] INSIDE router learned DMZ and outside routes.
- [x] DHCP relay provided valid inside client leases.
- [x] Inside client reached DHCP server `172.16.10.10`.
- [x] Inside client reached DNS server `172.16.10.7`.
- [x] Inside client reached external host `8.8.8.8`.
- [x] DMZ server reached ASA DMZ gateway `172.16.10.1`.
- [x] Outside host could not initiate traffic to inside gateway.
- [x] Capture a correct DMZ-to-inside denial using `192.168.100.15`.
- [x] Add the final Packet Tracer `.pkt` file.

Suggested evidence commands:

```cisco
show ip
show route
show ospf neighbor
show nat
show run | include access-list
show run | include access-group
show running-config
```
