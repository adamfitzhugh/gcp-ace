# IAM - Identity Access Management

* IAM Intro

    * Lets you grant specific access to Google Cloud resources and helps prevent access to other resources

    * Examples of resources include everything from VM's and cloud storage to folders and projects

    * Permissions aren't granted directly to the user. They're grouped into roles and roles are granted to members. 

    * A policy defines what roles are given to which members and the policy is attached to a resource


* IAM Model

    * Member - Includes a Google account, service account, group, g Suite/Cloud identity domain that can access a resource

    * Role - Collection of permissions which determine what operations are allowed on a specific resource

    * Policy - Binds one or more members to a role. You define which members have what access to what resources


* Accounts

    * Google Account - Anyone who interacts with Google Cloud who has a valid e-mail address

    * Service Account - An account which belongs to an application instead of an individual user

    * Google Group - Collection of service accounts and Google accounts. Conveninent way to apply a policy to a number of users

    * G Suite Domain - A virtual group of all Google accounts that have been created in an organisation's G Suite account. It represents your organisations internet domain (example.com)

    * Cloud Identity Domain - Same as G Suite domain except a Cloud Identity domain doesn't have access to G Suite applications and features

    * allAuthenticatedUsers - Represents anyone on the internet who has authenticated with a valid Google account

    * allUsers - Represents anyone on the internet whether authenticated or not


* Access Management Concepts

    * Resources

        * You can grant granular access to specific resources. For example you could grant a user admin rights to a particular storage bucket. 
    
        * You can also be less granular and assign permissions at a project level and permissions are inherited by all resources within that project

    * Permissions

        * Determine what operations are allowed on a resource

        * service.resource.verb

            * Example - pubsub.subscriptions.consume
        
        * You identify roles that contain appropriate permissions as oppose to granting permissions directly to a user

    * Roles

        * Collection of permissions

        * 3 types of roles:

            * Primitive Roles - Owner, Editor and Viewer. Avoid if possible as these are legacy and contain a wide range of permissions

            * Predefined Roles - These give finer-grained access. These are automatically updated when new features or services are added to Google

            * Custom Roles - Roles which you create to tailor your needs in an organisation. These are NOT maintained by Google. You will need the iam.roles.create in order to create custom roles

    * IAM Policy

        * You grant roles to users by creating an IAM policy. This is a collection of statements which define who has what access

        * A Cloud IAM policy is represented by a Cloud IAM policy object which contains a list of bindings:

            * Role - The role you want to give to the user. For example roles/service.roleName

            * Members - A list of one or more identities from user, serviceAccount, group or domain (G Suite/Cloud Identity domain)
        
    
    * Cloud IAM

        * Provides a set of methods you use to create and manage access control policies on resources

        * Cloud IAM Methods:

            * setIamPolicy():
            * getIamPolicy():
            * testIamPermissions():
        
    
    * Policy Hierarchy

        * Organisation > Folders > Projects > Resources

        * You can set an IAM policy at any level in the hierarchy

        * Resources inherit policies of a parent resource

        * Child policies cannot restrict access given at a higher level
   
     * Understanding Custom Roles
        
        * You cannot grant custom roles from one project or organisation on a resource owned by a different project or organisation
        
        * Org Admin Role - only org admins can grant the Organisation Role Administrator role
        
        * Role Admin Role - allows you to administer custom roles for a project. This is used if you do not have an organisation
        
        * A permission might not be available to you for example it might be in beta or you have not enabled API for the service
        
        * The following permissions are NOT supported in custom roles:
            
            * iam.serviceAccounts.getAccessToken
            * iam.serviceAccounts.actAs
            * iam.serviceAccounts.signBlob
            * iam.serviceAccounts.signJwt
         
        * Some permissions are dependant on others. For example to update a Cloud IAM policy you need read-write capabilities along with the setIamPolicy permission
        
        * ID for custom role can be up to 64 characters long and must be unique. It can contain uppercase, lowercase, alphanumeric characters, underscored and periods. The role ID cannot be changed once created
        
        * You can delete a role but not create a new one with the same ID until after the 37-day deletion period
        
        * You can test a custom role as it includes a role.stage property. Setting the stage to ALPHA indicates the role is not ready for production. You can allow a small set of members to use the role
        
        * You can then change the stage to BETA (if the services are still in beta) or GA
        
