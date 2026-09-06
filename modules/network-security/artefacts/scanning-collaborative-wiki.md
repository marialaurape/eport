# Scanning and Collaborative Wiki Activity
## Unit 4

### Scan Results — Altoro Mutual (`demo.testfire.net`)

**Operating System**  
The external black-box assessment did not provide sufficient evidence to identify the underlying operating system reliably.

**Web server software**  
Nmap service detection identified Apache Tomcat/Coyote JSP engine 1.1 on ports 80 and 8080. The Coyote/1.1 identifier relates to the HTTP connector and does not establish the exact Tomcat release.

**CMS**  
No evidence of a conventional CMS such as WordPress or Drupal was identified. Altoro Mutual is a Java/JSP web application.

**Protection / CDN / proxy / firewall**  
DNS reconnaissance identified eight Akamai-managed nameservers. The large number of filtered ports and behaviour observed on port 443 were consistent with an intermediary edge or proxy layer limiting direct access to services.

**Hosting**  
Traceroute data and WHOIS analysis of the resolved IP address (`65.61.137.117`) indicated Rackspace infrastructure in Dallas-Fort Worth. The traceroute stopped responding after hop 22, limiting complete path analysis.

**Open ports**  
Nmap identified ports 80/tcp and 8080/tcp as open and serving the application. Port 443/tcp was open but reported as `tcpwrapped`. Port 8443/tcp was reachable but closed. The remaining tested ports were filtered. Ports 80 and 443 were expected for a public web application; direct exposure of the application on port 8080 was more noteworthy.

**Known vulnerabilities**  
The TLS certificate presented on port 443 had expired on 21 June 2026, which was a confirmed configuration finding. Historical documentation associated AltoroJ with Apache Tomcat 7.x, for which CVE-2020-1938 (Ghostcat) was investigated. However, the deployed Tomcat version could not be confirmed, so this was treated as a candidate, version-dependent exposure rather than a confirmed vulnerability.

**Software versions / patch status**  
The scan confirmed the Coyote/1.1 connector but did not reveal the exact Tomcat release. It was therefore not possible to determine reliably from the external scan whether the underlying Tomcat installation was fully patched.

## Reflection

### Did you have any issues or challenges with the scans?

The main challenge was determining how much confidence could be placed in service and version information obtained from an external scan. Nmap identified Apache Tomcat/Coyote JSP engine 1.1 on ports 80 and 8080, but the `Coyote/1.1` identifier describes the HTTP connector and does not establish the exact Apache Tomcat release. Port 443 was also reported as `tcpwrapped`, limiting service fingerprinting, while most tested ports were filtered.

This created a further challenge when correlating scan results with known vulnerabilities. Historical documentation associated AltoroJ with Tomcat 7.x and vulnerability research identified CVE-2020-1938 as potentially relevant, but the current Tomcat version could not be independently confirmed.

### How did you overcome them?

I treated automated fingerprinting as one source of evidence rather than as definitive proof. Nmap results were correlated with information gathered during earlier reconnaissance and with software and vulnerability documentation. Findings that could be directly verified, such as the exposed ports and expired TLS certificate, were separated from version-dependent vulnerabilities requiring additional validation.

CVE-2020-1938 was therefore treated as a candidate exposure rather than a confirmed vulnerability. I also documented where filtering or intermediary infrastructure limited the information available from an external black-box assessment.

### How will they affect your final report?

The activity reinforced the need to communicate different levels of evidential confidence in vulnerability reporting. The final report would distinguish confirmed findings, observations and candidate vulnerabilities rather than presenting every automated result as an exploitable weakness.

It also influenced the proposed remediation priorities. Confirmed issues could be addressed directly, while version-dependent findings would first require verification of the underlying software version and configuration. This approach should reduce false positives and make the resulting recommendations more proportionate and defensible.

---

[Return to Network Security](../)
