# ![Create-AWS-IAM-User](https://aws.amazon.com/iam/faqs/)
   <img src="/Image/IAM_Basic_Understanding.jpg" >

#### What is AWS Identity and Access Management (IAM)?
You can use AWS IAM to **securely control individual and group access to your AWS resources**. You can create and manage user identities ("IAM users") and grant permissions for those IAM users to access your resources. You can also grant permissions for users outside of AWS ( federated users). 

#### How do I get started with IAM?
To start using IAM, you must subscribe to at least one of the AWS services that is integrated with IAM. You then can create and manage users, groups, and permissions via IAM APIs, the AWS CLI, or the IAM console, which gives you a point-and-click, web-based interface. You can also use the visual editor to create policies. 

##### 1. First Log into AWS account with root user
   <img src="/Image/0.png" >

##### 2. Subscribe to at least one of the AWS services that is integrated with IAM
   <img src="/Image/2.png">

### 3. After that we will get a `IAM web-based interface`
   <img src="/Image/3.png">

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
   <img src="/Image/4.png">

#### 4.2. Click on `Create New Group`
   <img src="/Image/5.png">
   
#### 4.3. **`Set Group Name`** example: `Admin`
   <img src="/Image/6.png">

#### 4.4. Click on Next and `Set Policy`
   <img src="/Image/7.png">

#### 4.5. Click on Next Step and `Review` your created group
   <img src="/Image/9.png">

#### 4.6. Now we will get our newly created group
   <img src="/Image/10.png">

### 5. ![IAM Users](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html?icmpid=docs_iam_console):

An IAM user is an entity that you create in AWS. The IAM user represents the person or service who uses the IAM user to interact with AWS. 

#### 5.1. Click on Users
   <img src="/Image/11.png">

A primary use for IAM users is to give people the ability to sign in to the AWS Management Console for interactive tasks and to make programmatic requests to AWS services using the API or CLI. 
#### 5.2. Click on `Add user`
   <img src="/Image/12.png">

A user in AWS consists of a name, a password to sign into the AWS Management Console, and up to two access keys that can be used with the API or CLI. 
#### 5.3. Set user details 
#### User Name (We can create one or more users at a same time)
   <img src="/Image/13.png">


- **programmatic access**
Programmatic access allows you to invoke actions on your AWS resources either through an application that you write or through a third-party tool. You use an access key ID and a secret access key to sign your requests for authorization to AWS.

- **AWS Management Sonsole Access**
The AWS Management Console brings the unmatched breadth and depth of AWS right to your computer or mobile phone with a secure, easy-to-access, web-based portal. Discover new services, manage your entire account, build new applications, and learn how to do even more with AWS.
#### 5.4. Set `AWS Access Type`
   <img src="/Image/15.png">

**NOTE:** Select **`Console Password`** as ***`Custom Password`***.

**NOTE:** Uncheck **`Required Password Reset`** otherwise _it will reset password of IAM user everytime after login_

#### 5.5 .When you create an IAM user, you grant it permissions by making it a member of a group that has appropriate permission policies attached (recommended), or by directly attaching policies to the user. You can also clone the permissions of an existing IAM user, which automatically makes the new user a member of the same groups and attaches all the same policies. 
   <img src="/Image/17.png">

#### 5.6. Review User and click on Create User
   <img src="/Image/18.png">

#### 5.7. After clicking we will get **Success screen*
   <img src="/Image/19.png">

**NOTE:** ***Important point*** is as a IAM user we will get an **`Account ID: 707873*******`** that is unique id and with that id only IAM user can login into his AWS IAM account.
   <img src="/Image/20.png">

## How does an IAM user sign in?
To sign in to the AWS Management Console as an IAM user, you must provide your account ID or account alias in addition to your user name and password. When your administrator created your IAM user in the console, they should have provided you with your user name and the URL to your account sign-in page. That URL includes your account ID or account alias.
 
![https://My_AWS_Account_ID.signin.aws.amazon.com/console/](https://My_AWS_Account_ID.signin.aws.amazon.com/console/)
 
You can also sign in at the following general sign-in endpoint and type your account ID or account alias manually:
 
![https://console.aws.amazon.com/](https://console.aws.amazon.com/)
 
For convenience, the AWS sign-in page uses a browser cookie to remember the IAM user name and account information. The next time the user goes to any page in the AWS Management Console, the console uses the cookie to redirect the user to the account sign-in page.
 
Note: IAM users can still use the URL link provided to them by their administrator to sign in to the AWS Management Console. 

#### 6. Provide IAM user credentials
   <img src="/Image/20.png">

#### 7. Now you are in IAM AWS user account
   <img src="/Image/21.png">


## When to Create an IAM User (Instead of a Role)
Because an IAM user is just an identity with specific permissions in your account, you might not need to create an IAM user for every occasion on which you need credentials. In many cases, you can take advantage of IAM roles and their temporary security credentials instead of using the long-term credentials associated with an IAM user.

#### You created an AWS account and you're the only person who works in your account.
It's possible to work with AWS using the root user credentials for your AWS account, but we don't recommend it. Instead, we strongly recommend that you create an IAM user for yourself and use the credentials for that user when you work with AWS. For more information, see Security Best Practices in IAM.

#### Other people in your group need to work in your AWS account, and your group is using no other identity mechanism.
Create IAM users for the individuals who need access to your AWS resources, assign appropriate permissions to each user, and give each user his or her own credentials. We strongly recommend that you never share credentials among multiple users.

## When should I use an IAM user, IAM group, or IAM role?
An **IAM user** has permanent long-term credentials and is used to directly interact with AWS services. An **IAM group** is primarily a management convenience to manage the same set of permissions for a set of IAM users. An **IAM role** is an AWS Identity and Access Management (IAM) entity with permissions to make AWS service requests. IAM roles cannot make direct requests to AWS services; they are meant to be assumed by authorized entities, such as IAM users, applications, or AWS services such as EC2. Use IAM roles to delegate access within or between AWS accounts. 


## More about Learning JAVA follow [Instagram page](https://www.instagram.com/learning_with_devil/) 
## [Instagram](https://www.instagram.com/devil_bunnyy/)
