## HAPPY WG (Heuristics and Algorithms to Prioritize Protocol deploYment)

RFC 8305 defined “Happy Eyeballs Version 2”, a client algorithm for resolving
and connecting to a server with different server IP address options, aiming
to improve IPv6 usage without degrading connection success rates due to
misconfigured networks, clients, or servers.

Since the publication of RFC 8305, several changes to common protocols, clients, and 
server deployments have occurred that require a revision of the algorithm. Some 
of these include:

- Standardization and increased use of QUIC, which require updating the
  TCP-specific parts of Happy Eyeballs.
- Introduction of Service Binding DNS resource records (SVCB and HTTPS RRs) that
  provide richer service information and add priorities and parameters that
  will change the sorting of addresses for Happy Eyeballs.
- Preparations for the standardization of TLS Encrypted Client Hello, which
  can impact which servers a client is willing to connect to based on available
  security properties.
- Increased deployment and refinement of IPv6-only and IPv6-mostly networks.

The HAPPY working group will deliver an updated version of the Happy Eyeballs 
algorithm, "Happy Eyeballs Version 3", that incorporates changes to account for
these developments. The working group will focus on realistic network
scenarios and performance data measured in deployed networks.
Although the algorithm needs to be generally applicable, platform-specific or
deployment-specific considerations should be included in the core algorithm
document. The algorithm should have tunable input values that allow for variation
between clients, with defaults based on working group consensus for preferred
behaviors.

The working group will also document the impact of the Happy Eyeballs algorithm
on the detection of misconfigured deployments, such as networks with configured
(but non-functional) IPv6 connectivity. This can include recommendations for how
to report issues that might otherwise be hidden by the algorithm's automatic
failover. Any reporting mechanisms need to preserve user privacy,
accurately detect broken deployments, and produce actionable reports.

The working group will focus on a connection establishment algorithm that
starts with a fully-qualified domain name (FQDN) and ends with a single
established connection to a server. While the algorithm may
apply to scenarios with multiple network links, or pools of multiple
connections, specific mechanisms for such scenarios are out of scope
for the working group.

The updated algorithm is expected to have increased cross-functional scope,
beyond the original versions of the algorithm developed in V6OPS. The HAPPY
working group will review its work with groups such as V6OPS, 6MAN, TSVWG,
QUIC, HTTPBIS, DNSOP, and TLS. The working group should also coordinate with the
Security Area, specifically around the security considerations for TLS Encrypted
Client Hello and the behavior of the algorithm with secure protocols (TLS, QUIC,
etc).

The working group’s core deliverables are:

- A standards-track document for Happy Eyeballs Version 3
- An informational document that explains the impact of Happy Eyeballs
  on detecting and measuring broken deployments, with recommendations on how to
  report errors in a privacy-preserving, accurate, and actionable way.
