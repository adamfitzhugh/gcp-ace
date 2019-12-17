# Virtual Machines

* Instances
  * Each instance belongs to a GCP project.
  * A project can have one or more instances
  * Each GCE has a small boot persistent disk which contains the OS
  * You can add additional storage options to your instance if needed
  * You can also deploy images via Docker containers
  * When you stop an instance the instance moves to terminated state however just rebooting it leaves it in the running state
  * When resetting an instance the VM does not do a graceful shutdown of the OS, but it does retain persistent disk data
  * GCP does not cap VM instance inbound/outbound traffic. However for purposes of capacity planning you should assume an instance can handle no more than 10Gbps of external internet traffic
  * You can deploy either public or custom images on GCE
  * Support for public images is subject to the lifecycle of the OS. Google publishes monthly updated images. Images can still be made available if the OS enters the extended lifecycle stage however monthly updated images aren't provided.
  * Custom images can be used for importing your on-premises VM's to GCE
  * Image families help management of images by grouping related images together for roll forward and roll back purposes
  * An image family always points to the latest, non-deprecated version
  * Guest Environment - set of scripts, daemons and binaries which are automatically installed on VM instances. This makes a VM run properly on GCE
  * OS Inventory Management can be used to identify VM OS's, packages installed on an instance and generate/identify missing packages on an instance
  * Preemptible Instance - create and run instances at much lower price however Google can terminate these if it requires access to those resources for other tasks. An example of this could be batch processing. Without these instances it can still process tasks but at a slower rate
  Preemptible instances are also terminated after they run for 24 hours by default

* Live Migration
  * Keeps VM's running even when a system event occurs such as a hardware/software update
  * GCE will migrate your running instances to another host in the same zone rather than rebooting your VM's
  * Instances will remain running during:
    * Maintenance and upgrades
    * Network and power maintenance
    * Failed hardware
    * Host OS and BIOS upgrades
    * Security related updates
    * System configuration changes
  * Once a live migration has happened the system deletes the source VM

* Networks
  * A project can have up to 5 VPC networks and each GCE belongs to one VPC network
  * Instances in the same network communicate via a local area network protocol

* Instance Life Cycle
  * Provisioning - Resources being allocated for the instance
  * Staging - The instance is being prepared for first boot
  * Running - The instance is booted and running
  * Stopping - The instance is being stopped
  * Repairing - The instance is being repaired. This can happen due to an internal error
  * Terminated - The instance has been stopped by the uder or the instance encountered a failure
  
* Machine Type Families
  * General Purpose Machine Type (N & E series)
  * Custom Machine Type
  * Memory-optimised Machine Type (M series)
  * Compute-optimised Machine Type (C series)
 
