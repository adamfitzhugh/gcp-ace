# Virtual Machines

* Instances
  * Each instance belongs to a GCP project.
  * A project can have one or more instances
  * Each GCE has a small boot persistent disk which contains the OS
  * You can add additional storage options to your instance if needed
  * You can also deploy images via Docker containers
  * When you stop an instance the instance moves to terminated state however just rebooting it leaves it in the running state
  * When resetting an instance the VM does not do a graceful shutdown of the OS, but it does retain persistent disk data

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
 
