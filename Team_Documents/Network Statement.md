# Network Architecture Design Statement

## Executive Summary

  * Globex is a conglomerate of entities and business units, united in bringing order to the world stage. To this end, it is vital that a uniform networking concept be envsioned and implemented to preserve the productivity and security of Globex against the growing global reality of hactivists and Advanced Persistent Threats (APTs) seeking to profit of causing harm to Globex's reputation, presence, and impact around the world.

## Needs and Impact

## Needs

Globex has several needs to meet when designing network architecture to scale:

* Elastic/Scalable - Globex requires a highly elastic solution to address its connectivity of global assets. Our company will continue to move at the speed of innovation, and as such, will need to rapidly expand our architecture to include our new partners which may consist of inclusion to the Globex Architecture or temporary access to the architecture. 

 * Availability - Our chosen solution must also ensure all elements of our company are connected to each other.
       
 * Security - The influence and presence that Globex exerts worldwide lends itself to becoming the subject of attacks by hacktivists and APTs not only to elicit profit via ransomeware attacks but also to invade our systems and persist to perform espionage and sabotage at opportune times. Security is paramount and consistent measures to Identify and Authenticate are needed to verify that personnel are who they represent themselves to be. 

 * Flexibility - Our proposed system must also provide the maximum level of flexibility and independence so our Individual Business Units (IBUs) may operate in an environment of a high degree of autonomy.

 * Management -  Globex will maintain control and coordination with all entities and guests (contractors). Out of band solutions are encouraged to maintain positive control of all elements.

## Methodology
  ### Analyze Requirements
     
  * Transitioning Partner former Infrastructure

     When conducting a transition of assets from a partner, it is essential that Globex identify what elements will ultimately be incorporated into our company infrastructure and what elements will be archived. 

     * Globex Network Architecture Personnel will identify all:

        * On Premise Facilities
        * Cloud Architecture
        * VPN 
        
      and supervise the migration of apporoved aspects to Globex Network Architecture

 ### Logical Network Design
    
  1. Globex Infrastrucutre Elements:
     * **Globex Cloud (via AWS VPC) - Globex's Corporate Cloud (GCC)***: Globex elects to choose a cloud model for its secured infrastructure to meet its stated need to be highly elastic and rapidly scalable.

       * Create subnets - Subnetting is a security measure related to the "*Defense in Depth*" concept. The creation of subnets allows leveraging of firewalls (represented here by the element of "Security Groups") to manage authorized communication between the subnets.
     
         1. **"Public Subnets"** (1) - Our public subnet will function as a buffer zone or a **"DMZ"** to safeguard our assets on the Globex Internal Network. Here we will station our servers (Web, Domain, File, etc.) that will be able to access the Internet. Higher layers of security can be achieved by further subnetting this space (e.g. to create 'quarantine zones' during Incident Response, or 'sandboxes areas' in order to conduct testing prior to implementing a change.)

            * The Security Group of the Globex Cloud only allows for assets located in the "Public Subnet" to access the Internet. This is done to maintain

            * **Globex Internet Gateway (Globex IGW)**- This is the primary means of connecting the DMZ to the Internet outside of GCC. The Public Subnet uses the Globex IGW as a security boundary. While not the most secure form of connection, an IGW is still a point at which further measures (e.g. Intrusion Detection Systems or Intrusion Prevention Systems may be deployed to further secure the GCC.)
             
               * Network Address Translation (NAT) can also be configured on Globex IGWs to support security "*Defense in Depth*"

            * **Globex Virtual Private Network (VPN)-**  A more secure means of connecting to the DMZ is by **VPN**, which will connect here via ***Virtual Private Gateway (VGW)*** to enhance security by obscuring traversing the VPN while allowing transitioning assets access to our resources during migration to our Internal Networks. They can be added to Security Group (SG) allowlists to facilitate this. Globex VPNs (and partner VPNs) must use the IPSec protocol in order to be  (e.g. OpenSwan, StrongSwan, OpenVPN, pfSense, etc.). On AWS, these systems may work with a ***Customer Private Gateway (CGW)*** to assist in completing the VPN connection Globex's **VPG.**

              * **Captive Portal-** The VPN tunnel will have a **Captive Portal** enabled on it to increase Globex's security posture via *Defense in Depth*. Use of this Captive Portal will ensure that access is only achieved by users with written authorization (from Globex) and credentials granted by the Domain Controller. Use of **Captive Portal** in conjunction with Active Directory will identify and authenticate the user seeking access. 

              * Contractors may also apply for access to connect to our VPN in this DMZ area. Only with special written authorization will contractors access the Globex Internal Network Infrastrucutre (on a case-by-case basis only).  

            * **Security Groups (SGs)** of the Globex Cloud only allow for assets located in the "Public Subnet" to access the Internet. In this regard, they function primarly as firewalls- enforcing rules set to allow or deny certain types of traffic. 

              * **Public Security Group** - Configured on the Public Subnet 

              * **Private Security Group** - Configured on the Private Subnet

         2. "Private Subnets" (1) - Our private subnets will comprise the Globex Internal Network Infrastrucutre (GINI). This network is where the heart of Globex will operate.

            *  These private subnets can be further broken down to the Business Unit (BU) Level

               * Within Business Units, Organizational Units (OUs) may be further segmented into ***Virtual Local Area Networks (VLANs).***

      * **Endpoints in Globex's Public Subnets**
         * As stated before, endpoints in the Public Subnet area are likely to be Functional Servers (e.g. web servers, file servers, redundant servers, etc.), but the endpoints here could also be proxies, or remote Globex users connecting through the **Virtural Private Gateway**. Resources here can be further subnetted to support sandboxes, quarantine zones for incident response, and even guest access to Internet (in waiting rooms, lobbies, etc.)

      * **Endpoints in Globex's Private Subnets**
        * Most of Globex's on-premise workstations will be located here. Further subnetting may host closed-circuit resources, executive-level access, Company Intranet, and more.

  2. Existing Logical Network Element Details (Globex)

| Network Element Name | Description | IP Address (CIDR) | Operating System (OS) | ID |
|:----------------:|:---------------:|:---------------:|:---------------:|:----:|
| 10Globex VPC | Globex Corporate Network | 10.0.0.0/16 | AWS VPC | vpc-03c429b1e9fefca02
| GX Public subnet | Globex DMZ1 |10.0.1.0/24 | AWS VPC | subnet-0858c6b0d8519d865  
| GX Private subnet | Globex Internal | 10.0.3.0/24 | AWS VPC | subnet-032a266835b02d8b8
| Globex IGW | Unsecured Internet Connection | IGW IP address | AWS IGW | igw-011a8bf616b568d43
| Globex VGW | Globex Secure Connection (VPN) | VGW IP address | AWS VPG | vgw-070362c6caaaf9a5d
| Globex EC2-1 | Public subnet instance | 10.0.1.137 / 3.88.248.166 [Public IP] | AWS EC2 (AMI  Linux) | i-07b5a5c9c950cb2a9 | 
| Globex EC2-2 | Private subnet instance | 10.0.221.100 | AWS EC2 (AMI Linux) |
| Globex Domain Controller | Active Server Directory | Server IP address | Windows 19 Server 

### AWS Security Group1 (Private Subnet to Public Subnet)

 
| Rule | Source | Destination | Port | Protocol |Notes |
|:--------------:|:----------:|:------------:|:-----------:|:-----:|:-------:|
| Allow | 0.0.0.0/0 | 0.0.0.0/0 | 22 | TCP | SSH
| Allow | 0.0.0.0/0 | 0.0.0.0/0 | - | ICMP | ICMP

  
  3. Existing Logical Network Element Details (GreenGenius)

| Network Element Name | Description | IP Address (CIDR) | Operating System (OS) | ID |
|:----------------:|:---------------:|:---------------:|:---------------:|:----:|
| GreenGenius VPC | GreenGenius VPC | 172.31.0.0/16 | AWS VPC | vpc-0f78af57f6ecb08e6
| GreenGenius EC2-3 | GreenGenius Endpoint | 172.31.10.122 / 44.201.2.52 [Public IP] | AWS EC2 (AMI Linux) | 1-0c7c98f557a995e27
| GreenGenius CGW | GreenGenius Customer Gateway | BGP ASN 65000 / 44.201.2.52 [Public IP] | AWS CGW | cgw-00b24a574063b5f6d


  
## Physical Network Design
    
  1. On-Premise resources
        * As Globex continues to expand and partner with new companies to provide more capabilities, assessment of acquired Information Technology assets may prove to be inadequate for incorporation to either the GCC or GINI. In these cases, allowances must be made to bring the existing facilities up to a minimum standard while a transition plan is approved and implemented. 
        * Proper cataloguing of this equipment is essential to provide consistent support during the transition period.

  2. Globex Cloud
       * Ideally all new acquisitions with be compatible with the GCC Infrastrucutre outlined in this Network Architecture Design Statement.


## Evaluation Result & Discussion

  1. Yearly Assessments of this Network Architecture Design Statement will be conducted to keep pace with emerging trends, threats and opportunies to reduce Globex's attack surface.

## Version Control:
* 06/21/2023 - Ben Hobbs
* 06/24/2023 - Ben Hobbs
* 06/25/2023 - Ben Hobbs