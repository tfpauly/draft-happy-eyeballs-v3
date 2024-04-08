## HAPPY WG (Heuristics and Algorithms to Prioritize Protocol deploYment)

RFC 8305 defined “Happy Eyeballs Version 2”, which described a client algorithm for
asynchronously resolving and attempting connections to different server IP address
options, aiming to improve the chance that IPv6 was used without adding risk due to
misconfigured networks or servers. The algorithm was written to focus specifically
on optimizing TCP connection establishment. The name “happy eyeballs” itself refers
to how a user’s eyeballs are happier when content loads more quickly because they
don’t need to wait for timeouts due to misconfigured deployments.

Since the publication of RFC 8305, several changes to the common protocols and server
deployments have occurred that require a revision of the algorithm. Some of these
include:

- Standardization of QUIC
- Service Binding DNS resource records (SVCB and HTTPS RRs) that provide richer information about services and priorities
- Preparations for the standardization of TLS Encrypted Client Hello
- Increased deployment and refinement of IPv6-only or IPv6-mostly networks

The HAPPY working group will deliver an updated version of the Happy Eyeballs algorithm
to incorporate the changes needed to account for these protocol developments. The
algorithm should be guided by data on what approaches work best on real networks,
and the working group will also consider how to report misconfigured deployments that
may be hidden by the automatic failover of the algorithm.

The work will be focused on connection establishment where the client knows a hostname
and needs to establish a connection to a server IP address over a particular network.
Algorithms for more general aspects of connection establishment attempts across multiple
networks, etc, are out of scope.

The rationale for having a working group for this work, as opposed to hosting it in
V6OPS, is the increased cross-functional nature of the algorithm. As such, the HAPPY
working group will review its work with groups such as V6OPS, TSVWG, QUIC, HTTPBIS,
DNSOP, and TLS.

The working group’s core deliverables are:

- Develop a new standards-track document for Happy Eyeballs Version 3
- Share measurements on the effectiveness of the algorithm during development
- Document approaches for reporting misconfigured networks or server deployments
