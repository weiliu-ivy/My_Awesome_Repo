Rekhter, et al.             Standards Track                     [Page 4]

RFC 4271                         BGP-4                      January 2006


      use several IGPs and, sometimes, several sets of metrics within an
      AS.  The use of the term Autonomous System stresses the fact that,
      even when multiple IGPs and metrics are used, the administration
      of an AS appears to other ASes to have a single coherent interior
      routing plan, and presents a consistent picture of the
      destinations that are reachable through it.

   BGP Identifier
      A 4-octet unsigned integer that indicates the BGP Identifier of
      the sender of BGP messages.  A given BGP speaker sets the value of
      its BGP Identifier to an IP address assigned to that BGP speaker.
      The value of the BGP Identifier is determined upon startup and is
      the same for every local interface and BGP peer.

   BGP speaker
      A router that implements BGP.
