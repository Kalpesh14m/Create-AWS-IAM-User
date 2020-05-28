# ![Create-AWS-IAM-User](https://aws.amazon.com/iam/faqs/)
   <img src="/Image/IAM_Basic_Understanding.jpg" width="500" height="250">

#### What is AWS Identity and Access Management (IAM)?
You can use AWS IAM to **securely control individual and group access to your AWS resources**. You can create and manage user identities ("IAM users") and grant permissions for those IAM users to access your resources. You can also grant permissions for users outside of AWS ( federated users). 

#### How do I get started with IAM?
To start using IAM, you must subscribe to at least one of the AWS services that is integrated with IAM. You then can create and manage users, groups, and permissions via IAM APIs, the AWS CLI, or the IAM console, which gives you a point-and-click, web-based interface. You can also use the visual editor to create policies. 

##### 1. First Log into AWS account with root user
   <img src="/Image/0.png" width="400" height="300">

##### 2. Subscribe to at least one of the AWS services that is integrated with IAM
   <img src="/Image/2.png" width="400" height="300">

### 3. After that we will get a `IAM web-based interface`
   <img src="/Image/3.png" width="400" height="200">

#### What is a group?

   An IAM group is a collection of IAM users. You can use groups to specify permissions for a collection of users, which can make those permissions easier to manage for those users. For example, you could have a group called Admins and give that group the types of permissions that administrators typically need. Any user in that group automatically has the permissions that are assigned to the group. If a new user joins your organization and should have administrator privileges, you can assign the appropriate permissions by adding the user to that group. Similarly, if a person changes jobs in your organization, instead of editing that user's permissions, you can remove him or her from the old groups and add him or her to the appropriate new groups. Note that a group is not truly an identity because it cannot be identified as a Principal in a resource-based or trust policy. It is only a way to attach policies to multiple users at one time. 

![A group](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html) is a collection of IAM users. Manage group membership as a simple list:
- Add users to or remove them from a group.
- A user can belong to multiple groups.
- Groups cannot belong to other groups.
- Groups can be granted permissions using access control policies. This makes it easier to manage permissions for a collection of users, rather than having to manage permissions for each individual user.
- Groups do not have security credentials, and cannot access web services directly; they exist solely to make it easier to manage user permissions. For details, see Working with Groups and Users.

### 4. How to create groups
<img src="/Image/4.png" width="400" height="200">
