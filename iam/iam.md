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

    
    * Service Accounts

        * An account used by an application or VM instance, NOT a person. Used for making authorised API calls

        * Identified by e-mail address which is unique to the account

        * Difference between User and Service account

            * Service accounts do not have passwords and cannot log in via browsers

            * Associated with private/public RSA key-pairs that are used for authentication to Google

            * Cloud IAM permissions can be granted to allow other users to impersonate a service account

            * Service accounts are NOT members of G Suite domain unlike user accounts

        * Types of Service Account Keys

            * Each SA is associated with two sets of public/private key pairs that are used to authenticate to Google - Google-managed keys and user-managed keys

            * Google-managed Keys - Google stores the public/private keys and rotate them regularly

            * User-managed Keys - Imply you own the public/private parts of the key pair. Google only stores the public part of a user-managed key. Using user-managed keys can represent a security risk if not managed correctly
        
        * Types of Service Accounts

            * User-managed Service Accounts
                
                * When you create a new project, if the Compute Engine API is enabled a Compute Engine SA is created for you by default using the identifier PROJECT_NUMBER-compute@developer.gserviceaccount.com

                * If your project contains an App Engine application the App Engine SA is created by default using the identifier PROJECT_ID@appspot.gserviceaccount.com

                * If you create a service account you'll name the SA and it will be assigned an e-mail with the following format SERVICE_ACCOUNT_NAME@PROJECT_ID.iam.gserviceaccount.com

                * You can create up to 100 service accounts per project
            
            * Google-managed Service Accounts

                * Google create and own service accounts which represent different Google services and each account is granted IAM roles to access your Google Cloud project

                * An example of a Google-managed SA is a Google API service account using the identifier PROJECT_NUMBER@cloudservices.gserviceaccount.com. This account is used to run internal Google processes and is not listed in the Service Accounts section of the console. This account is deleted when the project is deleted

        * Service Account Permissions

            * If you want to allow your application to access a storage bucket, you grant the service account permissions to read the Cloud Storage bucket.

        
