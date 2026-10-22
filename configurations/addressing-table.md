# Addressing Table

| Device | Interface/role | Address | Gateway |
|---|---|---|---|
| ASA | INSIDE | `10.10.10.1/30` | — |
| ASA | DMZ | `172.16.10.1/28` | — |
| ASA | OUTSIDE | `20.20.20.1/30` | `20.20.20.2` default route |
| INSIDE router | ASA transit | `10.10.10.2/30` | OSPF |
| INSIDE router | Client LAN | `192.168.100.1/24` | — |
| ISP | ASA transit | `20.20.20.2/30` | — |
| ISP | External LAN | `8.8.8.1/24` | — |
| DNS server | DMZ | `172.16.10.7/28` | `172.16.10.1` |
| Web server | DMZ | `172.16.10.9/28` | `172.16.10.1` |
| DHCP server | DMZ | `172.16.10.10/28` | `172.16.10.1` |
