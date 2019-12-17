# Networking

## VPC

* Virtual version of a Data Centre network and provides connectivity for your VM instances, GKE clusters, AE instances and other resources within your project

* VPC Specifications
    * Include their own routes and firewall rules. These are not part of a particular region or zone
    * Subnets are regional
    * Resources within a VPC can communicate pending firewall rules
    * Instances with internal IP's can communicate to Google's API's and services
    * VPC networks can be connected to other VPC networks via VPC peering
    * An organisation can use a shared VPC to keep a VPC network in a common host project
    * VPC networks can be securely connected in hybrid environments using Cloud VPN or Cloud Interconnect
    * VPC networks only support IPv4 unicast traffic. They DO NOT support broadcast, multicast or IPv6 traffic within the network
    * It is possible to create an IPv6 address for a global load balancer

* Networks & Subnets
    * A network must have at least one subnet before you can use it
    * Auto mode VPC networks create subnets in each region automatically. These auto created subnets use a set of predefined ranges that with within 10.128.0.0/9
    * Custom mode VPC networks start with no subnets, allowing you full control of subnet creation. Recommended for production environments
    * You can switch from auto mode to custom mode but CANNOT change from custom mode to auto mode

* Default Network
    * By default (unless you switch it off) each new project creates a default network in auto mode

* Auto Mode VPC Network Advantages
    * In auto mode, the predefined ranges of subnets do not overlap the IP ranges that have different use cases such as Cloud VPN connections

* Custom Mode VPC Network Advantages
    * Having one subnet created in each region isn't necessary
    * Having new subnets auto created could overlap with IP's used by manually created subnets
    * You cannot connect auto mode VPC networks to one another

* Subnets & IP Ranges
    * When creating a subnet you must define a primary IP address range
    * Primary IP Addresses - can choose any private RFC 1918 block. These can be used for VM primary internal IP's, alias IP's and internal load balancer addresses
    * Secondary IP Addresses - Must be separate blocks from primary IP address range and can only be used for alias IP addresses
    * Reserved IP's - see image!

* Routing
    * Routes in GCP are divided into two categories: system-generated and custom
    * System generated routes include a default route and a subnet route. A subnet route is created for each IP range within a subnet. They define paths for traffic to reach VM's that use subnets
    * Custom routes are either static routes that you create manually or dynamic routes learned by your cloud routers.
    * Cloud routers share routes to your VPC networks and learn dynamic routes from connected networks when you connect your VPC network to another network
    * Regional Dynamic Routing is the default. Unless modified, each cloud router only shares the routes to on-premises subnets within its region
    * Global Dynamic Routing changes the behaviour. Routes to on-prem resources that they learn are available in ALL subnets in the VPC network, regardless of region

* Firewall Rules
    * Every VPC network has 2 implied firewall rules. One allows most egress traffic, and the other denies all ingress traffic.
    * You cannot delete the implied rules but you can override them
    * 