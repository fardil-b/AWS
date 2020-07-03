# Creating an S3 bucket for static website hosting

### Log in to your AWS Console and navigate to S3 console

![image](https://user-images.githubusercontent.com/61830624/86466016-216d1480-bd33-11ea-9010-df5ac2ed364b.png)

### Choose Create New Bucket

![image](https://user-images.githubusercontent.com/61830624/86466127-63965600-bd33-11ea-9a76-537ffeb80ddc.png)

### The Create bucket wizard opens.
![image](https://user-images.githubusercontent.com/61830624/86466554-1cf52b80-bd34-11ea-8857-0b31e9bfe7bc.png)

### Note: bucket names must be globally unique across all AWS accounts
#### The bucket name must:
* Be unique across all of Amazon S3.
* Be between 3 and 63 characters long.
* Not contain uppercase characters.
* Start with a lowercase letter or number.

#### In Region, choose the AWS Region where you want the bucket to reside

![image](https://user-images.githubusercontent.com/61830624/86486986-3199e980-bd5d-11ea-808c-93a670a26302.png)

### In Bucket settings for Block Public Access, choose the Block Public Access settings that you want to apply to the bucket.
#### we choose to enable public access
![image](https://user-images.githubusercontent.com/61830624/86487448-622e5300-bd5e-11ea-85f9-c777c2b4e090.png)

### The s3 bucket has been created 
![image](https://user-images.githubusercontent.com/61830624/86487607-de289b00-bd5e-11ea-9931-45f689d404be.png)

### Next step is to upload the index.html file in your S3 bucket
![image](https://user-images.githubusercontent.com/61830624/86499666-b94b1c80-bd8c-11ea-95aa-0fb66cd294a4.png)

### Head to the "Properties" tab for the bucket
#### Then click into the "Static website hosting"
![image](https://user-images.githubusercontent.com/61830624/86499777-41c9bd00-bd8d-11ea-82e8-6255d4aa55b3.png)
#### Now select "Use this bucket to host a website" and add the name of your index document
![image](https://user-images.githubusercontent.com/61830624/86499894-d7fde300-bd8d-11ea-8e96-83dff9fc57f2.png)

### Make the file accessible to the public by clicking on "Make Public"
![image](https://user-images.githubusercontent.com/61830624/86500054-c8cb6500-bd8e-11ea-8b70-8fa2a6c1dc6b.png)

### you can access your website through an Amazon S3 website endpoint
![image](https://user-images.githubusercontent.com/61830624/86500102-25c71b00-bd8f-11ea-9be1-cd9395056ff6.png)


