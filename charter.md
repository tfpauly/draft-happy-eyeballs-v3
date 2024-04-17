## HAPPY WG (Heuristics and Algorithms to Prioritize Protocol deploYment)

RFC 8305 defined “Happy Eyeballs Version 2”, which described a client algorithm 
for asynchronous resolution of and connection attempts to different server IP 
address options, aiming to improve IPv6 usage without adding risk due to 
misconfigured networks or servers. The algorithm focused specifically on 
optimizing TCP connection establishment. The name “happy eyeballs” itself refers
to how a user’s eyeballs are happier when content loads more quickly because 
they don’t need to wait for timeouts due to misconfigured deployments.

Since the publication of RFC 8305, several changes to common protocols and 
server deployments have occurred that require a revision of the algorithm. Some 
of these include:

- Standardization and increased use of QUIC, which require updating the
  TCP-specific parts of Happy Eyeballs.
- Introduction of Service Binding DNS resource records (SVCB and HTTPS RRs) that
  provide richer information about available services and record priorities
  and change the selection and sorting of addresses for Happy Eyeballs.
- Preparations for the standardization of TLS Encrypted Client Hello.
- Increased deployment and refinement of IPv6-only and IPv6-mostly networks.

The HAPPY working group will deliver an updated version of the Happy Eyeballs 
algorithm that incorporates changes to account for these protocol developments.
The algorithm should focus on deployed network scenarios and should be guided by
data on user experience focused performance in those scenarios. The working 
group will also document the impact of the Happy Eyeballs algorithm on the
detection of misconfigured deployments, and document recommendations on how
to report such cases that might otherwise be hidden due to automatic switching
from one technology to another.

The working group will focus on connection establishment where the client knows 
a hostname and needs to establish a connection to a server IP address using a 
particular network. Algorithms for more general aspects of connection 
establishment attempts across multiple networks, etc, are out of scope.

The rationale for having a working group for this work, instead of hosting it in
V6OPS, is the increased cross-functional nature of the algorithm. As such, the 
HAPPY working group will review its work with groups such as V6OPS, TSVWG, QUIC, 
HTTPBIS, DNSOP, and TLS.

The working group’s core deliverables are:

- Develop a standards-track document for Happy Eyeballs Version 3
- Measure the effectiveness of the algorithm during development. This effort
  does not necessarily need to lead to a published document, but should be
  captured in presentations, working group wikis, etc.
- Document approaches for reporting misconfigured networks or server deployments
