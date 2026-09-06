# Scanning Activities
## Unit 3 Reflection

### Activity Context

The activity used basic reconnaissance techniques including traceroute, DNS queries and WHOIS to establish baseline information about Altoro Mutual (`demo.testfire.net`) and its supporting infrastructure.

### Did you have any issues or challenges with the scans?

Yes. The main challenge was that several reconnaissance tools behaved differently when queried against the `demo.testfire.net` subdomain. `dig` queries for MX and NS records did not return the expected records, and an initial WHOIS query failed because WHOIS registration data applies to registered domains rather than individual subdomains. In addition, traceroute did not reach the final destination: after hop 22, the remaining hops returned no response.

### How did you overcome them?

I repeated the DNS and WHOIS queries against the registered root domain (`testfire.net`), which provided the relevant nameserver and registration information. For the incomplete traceroute, I correlated the last responding hops with WHOIS information for the resolved IP address. This provided sufficient evidence to associate the hosting infrastructure with Rackspace without assuming that traceroute had identified the complete network path.

I also avoided interpreting individual latency measurements too literally, since routing behaviour such as ECMP can affect traceroute results.

### How will they affect your final report?

These challenges demonstrated the limitations of relying on individual reconnaissance tools. In the final report, results would therefore be corroborated across DNS, WHOIS, traceroute and subsequent service scanning rather than presented in isolation. Where a tool could not provide definitive information, this would be documented as an assessment limitation rather than converted into an unsupported finding.

The activity also established useful baseline information about DNS, network routing and hosting that could be compared with later scanning results.

---

[Return to Network Security](../)
