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

#### Group:

   An IAM group is a collection of IAM users. You can use groups to specify permissions for a collection of users, which can make those permissions easier to manage for those users. For example, you could have a group called Admins and give that group the types of permissions that administrators typically need. Any user in that group automatically has the permissions that are assigned to the group. If a new user joins your organization and should have administrator privileges, you can assign the appropriate permissions by adding the user to that group. Similarly, if a person changes jobs in your organization, instead of editing that user's permissions, you can remove him or her from the old groups and add him or her to the appropriate new groups. Note that a group is not truly an identity because it cannot be identified as a Principal in a resource-based or trust policy. It is only a way to attach policies to multiple users at one time.
   
![](https://user-images.githubusercontent.com/25608527/83198097-3109a400-a15c-11ea-864f-2f5c1fa0f583.png)

![A group](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html) is a collection of IAM users. Manage group membership as a simple list:
- Add users to or remove them from a group.
- A user can belong to multiple groups.
- Groups cannot belong to other groups.
- Groups can be granted permissions using access control policies. This makes it easier to manage permissions for a collection of users, rather than having to manage permissions for each individual user.
- Groups do not have security credentials, and cannot access web services directly; they exist solely to make it easier to manage user permissions. For details, see Working with Groups and Users.

### 4. How to create groups
#### 4.1. Click on `Group`
   <img src="/Image/4.png" width="400" height="200">

#### 4.2. Click on `Create New Group`
   <img src="/Image/5.png" width="400" height="200">
   
#### 4.3. **`Set Group Name`** example: `Admin`
   <img src="/Image/6.png" width="400" height="200">

#### 4.4. Click on Next and `Set Policy`
   <img src="/Image/7.png" width="400" height="200">

#### 4.5. Click on Next Step and `Review` your created group
   <img src="/Image/9.png" width="400" height="200">

#### 4.6. Now we will get our newly created group
   <img src="/Image/10.png" width="400" height="200">

### 5. IAM Users:

An IAM user is an entity that you create in AWS. The IAM user represents the person or service who uses the IAM user to interact with AWS. 

#### 5.1. Click on Users
   <img src="/Image/11.png" width="400" height="200">

A primary use for IAM users is to give people the ability to sign in to the AWS Management Console for interactive tasks and to make programmatic requests to AWS services using the API or CLI. 
#### 5.2. Click on `Add user`
   <img src="/Image/12.png" width="400" height="200">

A user in AWS consists of a name, a password to sign into the AWS Management Console, and up to two access keys that can be used with the API or CLI. 
#### 5.3. Set user details 
#### User Name (We can create one or more users at a same time)
   <img src="/Image/13.png" width="400" height="200">


- **programmatic access**
Programmatic access allows you to invoke actions on your AWS resources either through an application that you write or through a third-party tool. You use an access key ID and a secret access key to sign your requests for authorization to AWS.

- **AWS Management Sonsole Access**
The AWS Management Console brings the unmatched breadth and depth of AWS right to your computer or mobile phone with a secure, easy-to-access, web-based portal. Discover new services, manage your entire account, build new applications, and learn how to do even more with AWS.
#### 5.4. Set `AWS Access Type`
   <img src="/Image/15.png" width="400" height="200">

**NOTE:** Select **`Console Password`** as ***`Custom Password`***.

**NOTE:** Uncheck **`Required Password Reset`** otherwise _it will reset password of IAM user everytime after login_

#### 5.5 .When you create an IAM user, you grant it permissions by making it a member of a group that has appropriate permission policies attached (recommended), or by directly attaching policies to the user. You can also clone the permissions of an existing IAM user, which automatically makes the new user a member of the same groups and attaches all the same policies. 
   <img src="/Image/17.png" width="400" height="200">

#### 5.6. Review User and click on Create User
   <img src="/Image/18.png" width="400" height="200">

#### 5.7. After clicking we will get **Success screen*
   <img src="/Image/19.png" width="400" height="200">

**NOTE:** ***Important point*** is as a IAM user we will get an **`Account ID: 707873*******`** that is unique id and with that id only IAM user can login into his AWS IAM account.
   <img src="/Image/20.png" width="400" height="200">

#### 6. Provide IAM user credentials
   <img src="/Image/20.png" width="400" height="200">

#### 7. Now you are in IAM AWS user account
   <img src="/Image/21.png" width="400" height="200">

