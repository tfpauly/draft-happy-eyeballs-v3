## HAPPY WG (Heuristics and Algorithms to Prioritize Protocol deploYment)

RFC 8305 defined “Happy Eyeballs Version 2”, which described a client algorithm 
for asynchronous resolution of and connection attempts to different server IP 
address options, aiming to improve IPv6 usage without degrading connection
establishment success rates due to misconfigured networks, clients, or servers.
The algorithm focused specifically on optimizing TCP connection establishment.
The name “happy eyeballs” itself refers to how a user’s eyeballs are happier
when content loads more quickly because they don’t need to wait for timeouts
due to misconfigured deployments.

Since the publication of RFC 8305, several changes to common protocols, clients, and 
server deployments have occurred that require a revision of the algorithm. Some 
of these include:

- Standardization and increased use of QUIC, which require updating the
  TCP-specific parts of Happy Eyeballs.
- Introduction of Service Binding DNS resource records (SVCB and HTTPS RRs) that
  provide richer information about available services and record priorities
  and change the selection and sorting of addresses for Happy Eyeballs.
- Preparations for the standardization of TLS Encrypted Client Hello, which
  can impact which servers a client is willing to connect to based on available
  security properties.
- Increased deployment and refinement of IPv6-only and IPv6-mostly networks.

The HAPPY working group will deliver an updated version of the Happy Eyeballs 
algorithm, "Happy Eyeballs Version 3", that incorporates changes to account for
these protocol developments. The working group will focus on realistic network
scenarios and should be guided by performance data measured in deployed networks.
Although the algorithm needs to be generally applicable, platform-specific or
deployment-specific considerations should be included in the core algorithm
document. The algorithm should have tunable input values that can reflect the
preferences of a client implementation; defaults for these input values should
be based on working group consensus for standard behavior (such as preferring
IPv6 connections, preferring faster establishment times, etc.), but allow for
variation.

There have been a number of documents in which similar Happy Eyeballs-like racing
strategies have been specified, including in Section 4.3 of RFC 9132. An inventory
of such Happy Eyeballs-related use cases and a survey of other applications of
similar concepts are also in scope, which can be included as part of the Happy
Eyeballs Version 3 main deliverable.

The working group will also document the impact of the Happy Eyeballs algorithm
on the detection of misconfigured deployments, such as networks with configured
(but non-functional) IPv6 connectivity. It may provide recommendations for methods
or define protocols to report such cases that might otherwise be hidden due to 
automatic switching from one technology to another. Any reporting mechanisms
need to preserve user privacy, allow for accurate detection of broken deployments,
and produce reports that are actionable.

The working group will focus on a connection establishment algorithm that
runs on clients. The algorithm takes as input a fully-qualified domain name
(FQDN), and results in a single established connection to a single server IP
address on a single network. While the algorithm could apply to scenarios with
multiple networks to choose between or to use simultaneously, or could deal
with pools of multiple connections, such scenarios are out of scope for the
working group deliverables.

The updated algorithm is expected to have increased cross-functional scope,
beyond the original versions of the algorithm developed in V6OPS. As such, the 
HAPPY working group will review its work with groups such as V6OPS, 6MAN, TSVWG,
QUIC, HTTPBIS, DNSOP, and TLS. The working group should also coordinate with the
Security Area, specifically around the security considerations for TLS Encrypted
Client Hello and the behavior of the algorithm with secure protocols (TLS, QUIC,
etc).

The working group’s core deliverables are:

- A standards-track document for Happy Eyeballs Version 3
- An informational document that explains the impact of Happy Eyeballs
  on detecting and measuring broken deployments, with recommendations on how to
  report errors in a privacy-preserving, accurate, and actionable way.
