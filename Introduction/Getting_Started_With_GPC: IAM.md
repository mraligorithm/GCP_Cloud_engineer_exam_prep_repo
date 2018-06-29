# Getting_Started_With_GPC: IAM
- - - -
# Identity and Access Management (IAM)
Why is this important?
		* Any organization needs to control access to who access what resources. This is true in both inside and outside the technology realm.
		* Cloud IAM lets you adopt the security principle of least privilege, so you grant only the necessary access to your resources and prevent unwanted access to other resources. IAM allows you to meet compliance clauses around the separation of duty.
		* A more basic way of stating is that IAM lets you manage access control by defining who (members) has what access (role) for which resource.

##### Let’s break down those categories:
-> How is access managed?
		* Members (who), are granted permissions and roles (what)

-> What are members?
	* Google account
		* A Google account represents a developer, an administrator, or any other person who interacts with Google Cloud Platform. An email address that is associated with a Google account, such as a gmail.com address, can be an identity. New users can sign up for a Google account by going to the Google account signup page.

	* Service account
		* A service account is a special type of Google account that belongs to your application or a virtual machine (VM), instead of to an individual end user. Your application calls Google APIs assuming the identity of the service account, so that the users aren’t directly involved.
		* Provide an identity for carrying out server-to-server interactions in a project
		* Used to authenticate from one service to another
		* Can be used with primitive and curated roles
		* Identified with an email address:
			* @developer.gserviceaccount.com
			* @developer.gserviceaccount.com
		* A service account is an account that belongs to your application instead of to an individual end user. When you run code that is hosted on Cloud Platform, you specify the account that the code should run as. You can create as many service accounts as needed to represent the different logical components of your application. See the Google Cloud Platform Console Service Accounts documentation for more information.

	* Google group
		* A Google group is a named collection of Google accounts and service accounts. Every group has a unique email address that is associated with the group. You can find the email address that is associated with a Google group by clicking About on the homepage of any Google group. For more information about Google groups, see the Google groups homepage.

		* Google groups are a convenient way to apply an access policy to a collection of users. You can grant and change access controls for a whole group at once instead of granting or changing access controls one-at-a-time for individual users or service accounts. You can also easily add members to and remove members from a Google group instead of updating a Cloud IAM policy to add or remove users.

		* Note that Google groups don’t have login credentials, and you cannot use Google groups to establish identity to make a request to access a resource.

* G Suite domain
		* A G Suite domain represents a virtual group of all the members in an organization. G Suite customers can associate their email accounts with an Internet domain name. When you do this, each email account takes the form username@yourdomain.com. You can specify an identity by using any Internet domain name that is associated with a G Suite account.

		* Like groups, domains cannot be used to establish identity, but they enable convenient permission management.

* Cloud Identity Domain
		* A Cloud Identity domain is like a G Suite domain because it represents a virtual group of all members in an organization. However, Cloud Identity domain users don’t have access to G Suite applications and features.


**Roles**
	* Primitive Roles
		* Owner
		* Editor
		* Viewer
		* Billing Administrator
		* A project can have multiple owners, editors, viewers and billing administrators.
		* Primitive roles: The roles historically available in the Google Cloud Platform. Console will continue to work. These are the Owner, Editor, and Viewer roles.
		* Predefined roles: Predefined roles are the new IAM roles that give finer-grained access control than the primitive roles. For example, the predefined role Publisher provides access to only publish messages to a Pub/Sub topic.
		* Prior to Cloud IAM, you could only grant Owner, Editor, or Viewer roles. These roles give very broad access on a project and did not allow separation of duties. Cloud Platform services now offer additional roles that give finer-grained access control than the Owner, Editor, and Viewer roles. For example, Compute Engine offers roles such as Instance Admin and Network Admin and App Engine offers roles such as App Admin and Service Admin. These predefined roles are available in addition to the legacy Owner, Editor, and Viewer roles.

When would I use primitive roles?
Use primitive roles in the following scenarios:
	* When the Cloud Platform service does not provide a predefined role. See the predefined roles table for a list of all available predefined roles.
	* When you want to grant broader permissions for a project. This often happens when you’re granting permissions in development or test environments.
	* When you need to allow a member to modify permissions for a project, you’ll want to grant them the owner role because only owners have the permission to grant access to other users for for projects.
	* When you work in a small team where the team members don’t need granular permissions.

IAM Roles - Predefined Roles
	* Much more granular access, prevent unwanted access to other resources
			* Granted at resource level
* Example: App Engine Admin – Full access to only App Engine resources
* Multiple predefined roles can be given to individual users
* All current Predefined Roles - https://cloud.google.com/iam/docs/understandingroles#predefined_roles

IAM Policy
	* You can grant roles to users by creating a Cloud IAM policy, which is a collection of statements that define who has what type of access. A policy is attached to a resource and is used to enforce access control whenever that resource is accessed.

IAM Policy Hierarchy
	* Cloud Platform resources are organized hierarchically, where the Organization node is the root node in the hierarchy, the projects are the children of the Organization, and the other resources are the children of projects. Each resource has exactly one parent.

	* You can set an IAM access control policy at any level in the resource hierarchy: the Organization level, the project level or the resource level. Resources inherit the policies of the parent resource. If you set a policy at the organization level, it is automatically inherited by all its children projects, and if you set a policy at the project level, it is inherited by all its children resources. The effective policy for a resource is the union of the policy set at that resource and the policy inherited from its parent. This policy inheritance is transitive; in other words, resources inherit policies from the project, which inherit policies from the organization. Therefore, the organization-level policies also apply at the resource level.

	* For example, consider a Pub/Sub resource that lives under the project example-test. If you grant the editor role to bob@gmail.com for example-test, and grant the publisher role to alice@gmail.com for topic_a, you effectively grant editor role to bob@gmail.com and publisher role to alice@gmail.com for topic_a.

	* The IAM policy hierarchy follows the same path as the Cloud Platform resource hierarchy. If you change the resource hierarchy, the policy hierarchy changes as well. For example moving a project into an organization will update the project’s IAM policy to inherit from the organization’s IAM policy.

	* Child policies cannot restrict access granted at the parent. For example, if you grant editor role to a user for a project, and grant viewer role to the same user for a child resource, then the user still has editor role for the child resource.
#cloud/gcloud/architect_exam