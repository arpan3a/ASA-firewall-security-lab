# Firewall Traffic Policy

## Trust model

- INSIDE: security level 100
- DMZ: security level 70
- OUTSIDE: security level 0

## Approved flows

| Flow | Policy reason |
|---|---|
| Inside to DMZ | Trusted clients access approved servers |
| Inside to outside | Client internet access |
| DHCP server to relay `10.10.10.2` UDP/67 | Required DHCP relay response |
| DMZ to external DNS UDP/53 | Name resolution |
| DMZ to external HTTP TCP/80 and TCP/8080 | Approved web access |
| DMZ hosts to ASA DMZ interface via ICMP | Narrow troubleshooting exception |
| Inside network to ASA via SSH | Trusted administration |

## Denied flows

- General DMZ-initiated traffic to `192.168.100.0/24`
- Outside-initiated traffic to the inside network
- Outside SSH management
- All DMZ traffic not explicitly permitted by the ACL
