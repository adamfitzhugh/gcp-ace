# Instance-Groups

* Instance Group is a collection of machines you can manage as a single entity

* Unmanaged and managed instance groups
    * Managed Instance Groups - lets you operate apps on multiple, identical VM's. You can also take advantage of autoscaling, autohealing, regional zone deployment and auto updates
    * Unmanaged Instance Groups - lets you load balance across a fleet of VM's you manage yourself

* Benefits
    * Keeps instances running by automatically recreating a new instance if a current one crashes/fails according to the MIG spec
    * Create autohealing policies based on app health check which periodically verifies if an app responds as expected on each of the MIG instances
    * Regional/Multiple Zone Coverage
    * Load Balancing
    * MIGs can automatically scale based on application load to meet the group demand
    * The MIG automatic updater lets you safely deploy new versions of software to MIG instances in either a rolling or canary update fashion

* Autohealing
    * Along with whether an instance is up or not you may want to recreate instances that have froze, crashed or even ran out of memory. 
    * App based autohealing has a health check signal that detects application-specific issues such as freezing, crashing or overloading
    * The group will recreate an instance based on the above

* Health Checking
    * MIG health checks proactively signal to delete and recreate instances that become 'unhealthy'
    * MIG health checks and load balancing health checks are fairly similar, however try and keep these separated when configuring them
    * 

* Regional or Zonal Groups
    * Regional MIG - deploys instances to multiple zones acrss the same region. Offer 2000 instances per regional group
    * Zonal MIG - deploys instances to a single zone

* Load Balancing
    * You can use instance groups to serve traffic

* Autoscaling
    * Dynamically adds or removes instances from a MIG in response to increases or decreases in load
    * Policies include scaling based on CPU, load balancing capacity, Stackdriver monitoring

* Automatic Updating
    * The rollout of an update happens automatically based on spec. 
    * You can control the speed of the rollout to minimize disruption
    * You can also do partial rollouts which allows for canary testing

* Preemptible Instances
    * For workloads where cost is more important than speed, you can use preemptible VM instances
    * These last 24 hours and are preempted gracefully
    * Can be deleted at anytime although autohealing brings these back up when preemptible capacity becomes available again

* Containers
    * You can deploy containers to instances in MIGs
    * When you specify container image in instance template section it will create a MIG full of the container-optimised OS which includes Docker

* Network
    * By default instances are placed in the default network
    * You can restrict IP range of the group by creating a custom mode VPC network/subnet

* Unmanaged Instance Groups
    * Contain heterogeneous instances that you can add and remove from the group
    * Do not offer autoscaling, autohealing, rolling update support, multi-zone support, or use of instance templates
    * Use these if you need to apply load balancing to groups or if you need to manage the instances yourself
