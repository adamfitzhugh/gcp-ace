# GKE - Google Kubernetes Engine

* Provides a managed environment for deploying, managing and scaling contanerised applications using Google Cloud

* Cluster Orchestration with GKE

    * You can use Kubernetes commands to deploy, manage, perform admin tasks, set policies and monitor health of your workloads

    * Kubernetes on Google Cloud

        * Benefits of running Kubernetes on Google

            * GCP's load balancing for GCE
            * Node pools to designate subnets of nodes within a cluster for additional flexibility
            * Autoscaling of clusters
            * Automatic upgrades
            * Node auto-repair
            * Logging and monitoring with Stackdriver

        * GKE cluster masters are automatically upgrades to newer versions

    * GKE Workloads

        * Works with containerised applications by using Docker. 
        
        * Whether for applications or batch jobs these are called workloads

* Clusters

    * A cluster master runs the Kubernetes control plane processes including API, scheduler and core resource controllers

    * The master is the unified endpoint of your cluster. All interactions with the cluster are done by Kubernetes API calls

    * The API server is the single source of truth for the entire cluster

    * The cluster master is responsible for what runs on cluster nodes. This can include things such as upgrades, workloads and scheduled workloads

* Nodes

    * A cluster typically has one or more nodes which run your containerised applications and workloads

    * Default node machine type is n1-standard-1

* Pods

    * Represents a single instance of a running process in your cluster

    * Pods contain one or more containers. When a pod runs multiple containers the resources are shared. However doing this is an advanced use case

    * Pods also share networking and storage resources

    * Pods are automatically assigned IP addresses and pod containers share the same network namespace. Containers in a pod communicate via localhost

    * Pods can specify a set of shared storage volumes among containers

    * It is recommended that you create a set of identical pods (replicas) to run your application. This is managed by a controller such as a deployment

    * Pods run on nodes in your cluster. Once created, a pod remains on its node until its process is complete. If a node fails, pods on the node are automatically deleted

    * Pods are ephermeral and don't heal or repair themselves

    * Because pods are ephermeral it is not necessary to create pods directly. Instead you can use a controller, such as a deployment, which manages and creates the pods for you

    * When a pod starts running it requests CPU and memory requirements. This helps Kubernetes schedule a pod onto an appropriate node

* Deployments

    * Represent a set of identical pods

    * Runs multiple replicas of your application and automatically replace any failed or unresposive instances 

    * Managed by the Kubernetes deployment controller

    * Deployments use a pod template which specifies the pods configuration

    * When a deployments pod template is changed, new pods are automatically created one at a time

