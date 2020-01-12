# Associate Cloud Engineer Exam Guide

1. Setting up a cloud solution environment
    
    1.1 Setting up cloud projects and accounts. Activities include:

    * Creating projects
        
        * To create a project navigate to Select a Project and click New Project
    
    * Assigning users to predefined IAM roles within a project

        * From the left hand pane navigate to IAM & Admin > IAM > Add and specify your users and roles

    * Managing users in Cloud Identity (manually and automated)

        * From the left hand pane click IAM & Admin > IAM to view users and what roles are assigned to them
        * Clicking the roles tab shows the top level roles and what users/accounts are assigned to them

    * Enabling APIs within projects

        * From the left hand pane navigate to API's and services > Library & select your project
        * Search and click the API you want to enable
        * Click Enable

    * Provisioning one or more Stackdriver workspaces

        * From the left hand pane click Stackdriver > Monitoring and ensure a project is selected
        * Click the drop down next to the project name and select Create Workspace
        * Select your project and click Create Workspace

    1.2 Managing billing configuration. Activities include:

    * Creating one or more billing accounts

        * From the left hand pane click Billing console
        * Click Create account to create a new account
        * Self serve billing accounts are paid by credit/debit cards
        * Invoiced billing accounts are sent to customers

    * Linking projects to a billing account

        * From Billing page go to Account Management
        * Under 'Projects linked to this billing account' locate the project you want to move
        * Select 'Change billing' then choose the destination billing account

    * Establishing billing budgets and alerts

        * From the Billing page click Budgets & alerts
        * Click Create Budget
        * Specify the projects to associate with the alert
        * Specify cost amounts

    * Setting up billing exports to estimate daily/monthly charges

        * From the Billing page click Billing export
        * You can either export to Big Query or File Export, so choose which option you'd like

    1.3 Installing and configuring the command line interface (CLI), specifically the Cloud SDK (e.g., setting the default project).

        * Using Debian/Ubuntu - run 'apt-get'
        * Using Red Hat/CentOS - run 'yum'
        * Using Windows - download appropriate installer from cloud.google.com

        * Once installed, you will need to initialise the SDK using 'gcloud init' command
        * You are prompted to authenticate with Google when you go to the URL
        * Copy the response code into your terminal window
        * Next you are prompted to enter a project by either selecting an already existing one, or creating a new one (this will be your default project)


2. Planning and configuring a cloud solution
    
    2.1 Planning and estimating GCP product use using the Pricing Calculator

    2.2 Planning and configuring compute resources. Considerations include:

    * Selecting appropriate compute choices for a given workload (e.g., Compute Engine, Google Kubernetes Engine, App Engine, Cloud Run, Cloud Functions)
    * Using preemptible VMs and custom machine types as appropriate

    2.3 Planning and configuring data storage options. Considerations include:

    * Product choice (e.g., Cloud SQL, BigQuery, Cloud Spanner, Cloud Bigtable)
    * Choosing storage options (e.g., regional, multi-regional, nearline, coldline)

    2.4 Planning and configuring network resources. Tasks include:

    * Differentiating load balancing options
    * Identifying resource locations in a network for availability
    * Configuring Cloud DNS


3. Deploying and implementing a cloud solution

    3.1 Deploying and implementing Compute Engine resources. Tasks include:

    * Launching a compute instance using Cloud Console and Cloud SDK (gcloud) (e.g., assign disks, availability policy, SSH keys)
    * Creating an autoscaled managed instance group using an instance template
    * Generating/uploading a custom SSH key for instances
    * Configuring a VM for Stackdriver monitoring and logging
    * Assessing compute quotas and requesting increases
    * Installing the Stackdriver Agent for monitoring and logging

    3.2 Deploying and implementing Google Kubernetes Engine resources. Tasks include:

    * Deploying a Google Kubernetes Engine cluster
    * Deploying a container application to Google Kubernetes Engine using pods
    * Configuring Google Kubernetes Engine application monitoring and logging
    
    3.3 Deploying and implementing App Engine, Cloud Run, and Cloud Functions resources. Tasks include, where applicable:

    * Deploying an application, updating scaling configuration, versions, and traffic splitting
    * Deploying an application that receives Google Cloud events (e.g., Cloud Pub/Sub events, Cloud Storage object change notification events)

    3.4 Deploying and implementing data solutions. Tasks include:

    * Initializing data systems with products (e.g., Cloud SQL, Cloud Datastore, BigQuery, Cloud Spanner, Cloud Pub/Sub, Cloud Bigtable, Cloud Dataproc, Cloud Dataflow, Cloud Storage)
    * Loading data (e.g., command line upload, API transfer, import/export, load data from Cloud Storage, streaming data to Cloud Pub/Sub)

    3.5 Deploying and implementing networking resources. Tasks include:

    * Creating a VPC with subnets (e.g., custom-mode VPC, shared VPC)
    * Launching a Compute Engine instance with custom network configuration (e.g., internal-only IP address, Google private access, static external and private IP address, network tags)
    * Creating ingress and egress firewall rules for a VPC (e.g., IP subnets, tags, service accounts)
    * Creating a VPN between a Google VPC and an external network using Cloud VPN
    * Creating a load balancer to distribute application network traffic to an application (e.g., Global HTTP(S) load balancer, Global SSL Proxy load balancer, Global TCP Proxy load balancer, regional network load balancer, regional internal load balancer)

    3.6 Deploying a solution using Cloud Marketplace. Tasks include:

    * Browsing Cloud Marketplace catalog and viewing solution details
    * Deploying a Cloud Marketplace solution
    
    3.7 Deploying application infrastructure using Cloud Deployment Manager. Tasks include:

    * Developing Deployment Manager templates
    * Launching a Deployment Manager template


4. Ensuring successful operation of a cloud solution

    4.1 Managing Compute Engine resources. Tasks include:

    * Managing a single VM instance (e.g., start, stop, edit configuration, or delete an instance)
    * SSH/RDP to the instance
    * Attaching a GPU to a new instance and installing CUDA libraries
    * Viewing current running VM inventory (instance IDs, details)
    * Working with snapshots (e.g., create a snapshot from a VM, view snapshots, delete a snapshot)
    * Working with images (e.g., create an image from a VM or a snapshot, view images, delete an image)
    * Working with instance groups (e.g., set autoscaling parameters, assign instance template, create an instance template, remove instance group)
    * Working with management interfaces (e.g., Cloud Console, Cloud Shell, GCloud SDK)

    4.2 Managing Google Kubernetes Engine resources. Tasks include:

    * Viewing current running cluster inventory (nodes, pods, services)
    * Browsing the container image repository and viewing container image details
    * Working with node pools (e.g., add, edit, or remove a node pool)
    * Working with pods (e.g., add, edit, or remove pods)
    * Working with services (e.g., add, edit, or remove a service)
    * Working with stateful applications (e.g. persistent volumes, stateful sets)
    * Working with management interfaces (e.g., Cloud Console, Cloud Shell, Cloud SDK)

    4.3 Managing App Engine and Cloud Run resources. Tasks include:

    * Adjusting application traffic splitting parameters
    * Setting scaling parameters for autoscaling instances
    * Working with management interfaces (e.g., Cloud Console, Cloud Shell, Cloud SDK)

    4.4 Managing storage and database solutions. Tasks include:

    * Moving objects between Cloud Storage buckets
    * Converting Cloud Storage buckets between storage classes
    * Setting object life cycle management policies for Cloud Storage buckets
    * Executing queries to retrieve data from data instances (e.g., Cloud SQL, BigQuery, Cloud Spanner, Cloud Datastore, Cloud Bigtable)
    * Estimating costs of a BigQuery query
    * Backing up and restoring data instances (e.g., Cloud SQL, Cloud Datastore)
    * Reviewing job status in Cloud Dataproc, Cloud Dataflow, or BigQuery
    * Working with management interfaces (e.g., Cloud Console, Cloud Shell, Cloud SDK)
    
    4.5 Managing networking resources. Tasks include:

    * Adding a subnet to an existing VPC
    * Expanding a subnet to have more IP addresses
    * Reserving static external or internal IP addresses
    * Working with management interfaces (e.g., Cloud Console, Cloud Shell, Cloud SDK)

    4.6 Monitoring and logging. Tasks include:

    * Creating Stackdriver alerts based on resource metrics
    * Creating Stackdriver custom metrics
    * Configuring log sinks to export logs to external systems (e.g., on-premises or BigQuery)
    * Viewing and filtering logs in Stackdriver
    * Viewing specific log message details in Stackdriver
    * Using cloud diagnostics to research an application issue (e.g., viewing Cloud Trace data, using Cloud Debug to view an application point-in-time)
    * Viewing Google Cloud Platform status
    * Working with management interfaces (e.g., Cloud Console, Cloud Shell, Cloud SDK)
    

5. Configuring access and security
    
    5.1 Managing identity and access management (IAM). Tasks include:

    * Viewing IAM role assignments
    * Assigning IAM roles to accounts or Google Groups
    * Defining custom IAM roles

    5.2 Managing service accounts. Tasks include:

    * Managing service accounts with limited privileges
    * Assigning a service account to VM instances
    * Granting access to a service account in another project

    5.3 Viewing audit logs for project and managed services.