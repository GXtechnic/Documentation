# GXTechnic Network Architecture Statement 

## Executive Summary

  * Globex is a conglomerate of entities and business units, united in bringing order to the world stage. To this end, it is vital that a uniform networking concept be envsioned and implemented to preserve the productivity and security of Globex against the growing global reality of hactivists and Advanced Persistent Threats (APTs) seeking to profit of causing harm to Globex's reputation, presence, and impact around the world.

## Needs and Impact

Connectivity - Globex requires a highly elastic solution to address to connectivity of global assets. Our company will continue to move at the speed of innovation, and as such, will need to rapidly expand our architecture to include our new partners which may consist of inclusion to the Globex Architecture or temporary access to the architecture.

 * Our chosen solution must also ensure all elements of our company are connected to each other.
       
 * Security - The influence and presence the Globex exerts worldwide lends itself to becoming the subject of attacks by hacktivists and APTs not only to elicit profit via ransomeware attacks but also to invade our systems and persist to perform espionage and sabotage at opportune times. 

 * Flexibility - Our proposed system must also provide the maximum level of flexibility and independence so our Individual Business Units (IBUs) may operate in an environment of a high degree of autonomy.

 * Management -  Globex will maintain control and coordination with all entities and guests (contractors). Out of band solutions are encouraged to maintain positive control of all elements.

## Methodology
  ### Analyze Requirements
     
  * 

 ### Logical Network Design
    
  1. Globex Infrastrucutre
      
   * Elements:
     * Globex Cloud (via AWS VPC) - Globex's Corporate Cloud (GCC)

       * Create subnets

         1. "Public Subnets" (1) - Our public subnets will function as a buffer zone or a "DMZ" to safeguard our assets on the Globex Internal Network. Here we can station our servers (Web, Domain, File, etc.) that will be able to access the Internet. 
              
            * Globex VPN will connect here to allow transitioning assets access to our resources while migrating to our Internal Networks. They can be added to allowlists to facilitate this.

            * Most Contractors will connect to our VPN to this DMZ area. Only with special written authorization will contractors access the Internal Network (case-by-case basis only)  

         2. "Private Subnets" (1) - Our private subnets will comprise the Globex Internal Network Infrastrucutre (GINI). This network is where the heart of Globex will operate.

            *  These private subnets will be further broken down to the Business Unit Level

            * Organization Units or Departments within Business Units can be segmented via VLAN

      * Globex Internet Gateway (Globex IGW)
      * Endpoints in GX Public subnet
      * Endpoints in GX Private subnet

  2. Transitioning Partner former Infrastructure

     When conducting a transition of assets from a partner, it is essential that Globex identify what elements will ultimately be incorporated into our company infrastructure and what elements will be archived. 

     * Globex Network Architecture Personnel will identify all:

        * On Premise Facilities
        * Cloud Architecture
        * VPN 
        
      and supervise the migration of apporoved aspects to Globex Network Architecture

  3. Existing Logical Network Elements (Globex)

| Network Element Name | Description | IP Address (CIDR) | Operating System (OS) | Notes |
|:----------------------:|:-----------------------:|:----------------------:|:----------------------:|:----------------------:|
Globex VPC | Globex Corporate Network | 18.207.157.243/16 | AWS VPC | Example note |
GX Public subnet | Globex DMZ1 |10.0.0.0/17 | AWS VPC | what else here? | 
GX Private subnet | Globex Internal | 10.0.128.0/17 | AWS VPC | note3 | 
Globex IGW | | 10.0.0.0/16 | AWS IGW | | 
EC2-1 | Public subnet instance | 18.207.157.243 | AWS EC2 (AMI Linux) | 
EC2-2 | Private subnet instance | 10.0.221.100 | AWS EC2 (AMI Linux) |
EC2-3 | GreenGenius | 35.168.112.89 | AWS EC2 (AMI Linux) | 
 | Globex Domain Controller | Active Server Directory | | Windows 19 Server 


| Firewall 1 (Private Subnet to Public Subnet) |:-----------------:|:----------------------:|:---------------------:|:------------------:|:----------------------:| Rule | Source | Destination | Port | Notes |
 Allow | | 255.255.255.255/32 | AWS VPC | Note1 |

| DHCP | Description | IP Address (CIDR) | Operating System (OS) | Notes |
|:----------------------:|:-----------------------:|:----------------------:|:----------------------:|:----------------------:|
  
  
  4. 
  * Physical Network Design
    
    1. On-Premise resources

    2. Globex Cloud


## Evaluation Result & Discussion

  1. Yearly Assessment

## Version Control:
06/21/2023 - Ben Hobbs
06/24/2023 - Ben Hobbs