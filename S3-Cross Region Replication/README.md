# S3- Cross Region Replication (CRR)
## CRR is an automatic, __asynchronus__ copying of objects from a bucket in one region (soucre Bucekt) to another bucket in another region (Destination Bucket)
- asynchronus --> replication is not done at real time ( espect some delay bofore you see the replicated object)

## Why we need CRR?
* If you have an application where you are sending the files from one bucket in one region to another in a different region for post processing
* if you simply want to backup the objects in another region for disaster recovery

## Requirement for CRR
* soucre and destination buckets must be in different AWS Regions
* Both the source and destination buckets must have **versioning enabled**
* S3 must have permissions to replicate objects from that source bucket to the destination bucket in your behalf
* For a cross-amount scenerio, where source and destination buckets are owned by different AWS accounts, the IAM role must have to replicate objets in the destination bucket.

## What is replicated?
* Any new objects created after you add a replication configuration
* Unencrypted objects as well as encrypted objects- but only if they are encrypted with SSE-3, or SSE-KMS. If the object is the source bucket eas encrypted, the replication copy of theobjext is also encrpted using the same type of server-side encryption.
* Along with the objects,S3 also replicates object metadata
* S3 also replicates objects in the source bucket for which the bucket owner has permissions to read objects and read access control lists(ACLs)

## What is not replicated?
* obkects that existed before you added replication configuration
* Objects encrypted with SSE-C encryption
* Objects in the source bucket for which the bucket owner dies not have permissions
* Updates to bucket-level sub-resources are not repllicated
* Objects in the source bucket that are replicas, created by another cross-region replication

## Delete Operation and Cross-Region Replication
* For delete **without** version ID, S3 adds a delete marker, which cross-region replication replicates to the bucket destination buckets
* For delete **with** version ID, S3 deletes the object version in the source bucket, but it does not replicate the deletion in the destination bucket. 

Go to your S3 bucket in AWS Console, mke sure versioning is enabled
![image](https://user-images.githubusercontent.com/61830624/87338715-df6b7c00-c545-11ea-9e50-24274619c9ea.png)

![image](https://user-images.githubusercontent.com/61830624/87338966-33766080-c546-11ea-9549-da63533f0b40.png)

Create a new bucket for destination bucket or select one if you have
![image](https://user-images.githubusercontent.com/61830624/87339226-99fb7e80-c546-11ea-887e-3a71c4c96bd2.png)


![image](https://user-images.githubusercontent.com/61830624/87339412-da5afc80-c546-11ea-9aa9-afe06e258b3e.png)

