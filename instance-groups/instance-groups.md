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
    * 