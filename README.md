# My_Awesome_Repo

BGP-4 provides a new set of mechanisms for supporting Classless
   Inter-Domain Routing (CIDR) [RFC1518, RFC1519].  These mechanisms
   include support for advertising a set of destinations as an IP prefix
   and eliminating the concept of a network "class" within BGP.  BGP-4
   also introduces mechanisms that allow aggregation of routes,
   including aggregation of AS paths.

   This document uses the term `Autonomous System' (AS) throughout.  The
   classic definition of an Autonomous System is a set of routers under
   a single technical administration, using an interior gateway protocol
   (IGP) and common metrics to determine how to route packets within the
   AS, and using an inter-AS routing protocol to determine how to route
   packets to other ASes.  Since this classic definition was developed,
   it has become common for a single AS to use several IGPs and,
   sometimes, several sets of metrics within an AS.  The use of the term
   Autonomous System stresses the fact that, even when multiple IGPs and
   metrics are used, the administration of an AS appears to other ASes
   to have a single coherent interior routing plan and presents a
   consistent picture of the destinations that are reachable through it.

   BGP uses TCP [RFC793] as its transport protocol.  This eliminates the
   need to implement explicit update fragmentation, retransmission,
   acknowledgement, and sequencing.  BGP listens on TCP port 179.  The
   error notification mechanism used in BGP assumes that TCP supports a
   "graceful" close (i.e., that all outstanding data will be delivered
   before the connection is closed).

   A TCP connection is formed between two systems.  They exchange
   messages to open and confirm the connection parameters.

   The initial data flow is the portion of the BGP routing table that is
   allowed by the export policy, called the Adj-Ribs-Out (see 3.2).
   Incremental updates are sent as the routing tables change.  BGP does
   not require a periodic refresh of the routing table.  To allow local
   policy changes to have the correct effect without resetting any BGP
   connections, a BGP speaker SHOULD either (a) retain the current
   version of the routes advertised to it by all of its peers for the
   duration of the connection, or (b) make use of the Route Refresh
   extension [RFC2918].
