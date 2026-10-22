# Packet Tracer ASA Limitations

The simulated ASA 5506-X does not implement every command available on a physical ASA or ASAv. In this lab, the following were unavailable or incomplete:

- `packet-tracer input ...`
- `show conn`
- Some named ACL display and sequence insertion forms
- Static service NAT using `static interface service`
- NAT hit counters remained at zero in the observed simulation

Validation therefore used supported running-configuration filters, routing tables, OSPF neighbors, DHCP lease renewal, end-to-end pings, traceroute, and positive/negative traffic tests.
