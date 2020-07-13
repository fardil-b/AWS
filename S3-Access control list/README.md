# S3 - Permission: Access Control List and Bucket Policy
- Both Access Control list and Bucket Policy are resource-based policies
(Resouce Based Policies are applied to the resource itself, not to any user or role)

### What is ACL?
* It Enables you to manage access to buckets and objects. Each bucket and object has an ACL attached to it as a sub-resource
* It also defines which AWS accounts or groups are granted acccess and the type of access
* When a request is received against a resource, S3 checks the corresponding ACL to verify that the requester has the necessary access permissions

### What is Bucket policy?
* Grants other AWS accounts or IAM user access permissions for the bucket and the objects in it
* Object permissions apply only to the objects that the bucket owner creates

In AWS Console go to your bucket, in permissions section you can see that there is no Bucket Policy
![image](https://user-images.githubusercontent.com/61830624/87324028-d2dc2900-c52f-11ea-98c6-db026010b332.png)

Go to your bukcet ans Permissions, this show your current ACL configurations
![image](https://user-images.githubusercontent.com/61830624/87324245-1f276900-c530-11ea-830b-7c05c7345a53.png)

With this option you can give another AWS user access to your bucket
![image](https://user-images.githubusercontent.com/61830624/87324414-572eac00-c530-11ea-8b6f-3f9c4e14dacb.png)

Go to bucket policy, here you can insert your own bucket policy
![image](https://user-images.githubusercontent.com/61830624/87324564-8e04c200-c530-11ea-98fb-9f14d846d389.png)

Click on policy generator on the bottom of the page to create your own policy

![image](https://user-images.githubusercontent.com/61830624/87325060-429ee380-c531-11ea-979e-da8c5b7fecf3.png)

Generate the policy and copy the contents
![image](https://user-images.githubusercontent.com/61830624/87325347-9e696c80-c531-11ea-8bf3-9959e6b091b5.png)

Go to your bucket, permissions and bukcet policy and paste the generated policy
![image](https://user-images.githubusercontent.com/61830624/87325620-f43e1480-c531-11ea-9607-86f95d3567cf.png)

This bucket has a public access now
![image](https://user-images.githubusercontent.com/61830624/87326174-afff4400-c532-11ea-9d06-628f14cfa293.png)

If you want to make the bucket accessible to specific principle then instead of __*__ include that principal name
