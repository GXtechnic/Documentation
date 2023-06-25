#  Network Statement

## Executive Summary

* Globex is a conglomerate of entities and business units, united in bringing order to the world stage. To this end, it is vital that a uniform networking concept be envsioned and implemented to preserve the productivity and security of Globex against the growing global reality of hactivists and Advanced Persistent Threats (APTs) seeking to profit of causing harm to Globex's reputation, presence, and impact around the world.

## Needs and Impact

## Methodology

* Analyze Requirement
  * Connectivity - Globex requires a highly elastic solution to address to connectivity of global assets. Our company will continue to move at the speed of innovation, and as such, will need to rapidly expand our architecture to include our new partners which may consist of inclusion to the Globex Architecture or temporary access to the architecture.

    * Our chosen solution must also ensure all elements of our company are connected to each other.

  * Security - The influence and presence the Globex exerts worldwide lends itself to becoming the subject of attacks by hacktivists and APTs not only to elicit profit via ransomeware attacks but also to invade our systems and persist to perform espionage and sabotage at opportune times.

  * Flexibility - Our proposed system must also provide the maximum level of flexibility and independence so our Individual Business Units (IBUs) may operate in an environment of a high degree of autonomy.

  * Management -  Globex will maintain control and coordination with all entities and guests (contractors). O

* Logical Network Design

    1. Globex Infrastrucutre
        * Globex Cloud (via AWS VPC) - Globex's Corporate Cloud (GCC)

          * Create 6 subnets

            1. "Public Subnets" (2) - These public subnets will function as a buffer zone or a "DMZ" to safeguard our assets on the Globex Internal Network. Here we can station our servers (Web, Domain, File, etc.) that will be able to access the Internet.

               * Globex VPN will connect here to allow transitioning assets access to our resources while migrating to our Internal Networks. They can be added to allowlists to facilitate this.

               * Most Contractors will connect to our VPN to this DMZ area. Only with special written authorization will contractors access the Internal Network (case-by-case basis only)

            2. "Private Subnets" (4) - These private subnets will comprise the Globex Internal Network Infrastrucutre (GINI). This network is where the heart of Globex will operate.

    2. Transitioning Partner former Infrastructure
        * On Premise Facilities
        * Cloud Architecture
        * VPN access

* Physical Network Design

    1. On-Premise resources

    2. Globex Cloud

Evaluation Result & Discussion

  1. Yearly Assessment
