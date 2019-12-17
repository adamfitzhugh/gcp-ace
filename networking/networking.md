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
    * Auto mode VPC networks create subnets in each region automatically
    * Custom mode VPC networks start with no subnets, allowing you full control of subnet creation
    * 