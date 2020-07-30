## Amazon Auto Scaling
AWS Auto Scaling will automatically scale resources as needed to align to your selected scaling strategy. 
- Auto Scaling to automatically launch or terminate EC2 instances based on user-defined policies, schedules and health checks

Log in to AWS console, go to EC2 and Autoscaling , click on launch configuration
![image](https://user-images.githubusercontent.com/61830624/88928658-5bb9cb00-d279-11ea-832d-433b109f7978.png)
Create launch configuration
![image](https://user-images.githubusercontent.com/61830624/88928890-a63b4780-d279-11ea-910c-4e5741e1daa8.png)

Choose the autosclae Ami a pre-configured AMI
![image](https://user-images.githubusercontent.com/61830624/88929344-4beeb680-d27a-11ea-80e3-09129fc7979c.png)

Choose the instance type
![image](https://user-images.githubusercontent.com/61830624/88929225-1e097200-d27a-11ea-8406-5e4aa2841aab.png)

Create a new security group
![image](https://user-images.githubusercontent.com/61830624/88929584-9f610480-d27a-11ea-958c-3809c0df8293.png)

We don't need keypair so you can proceed without a key pair
![image](https://user-images.githubusercontent.com/61830624/88929701-c4ee0e00-d27a-11ea-926e-ca99ce2cc024.png)

Launch Configuration successfully created
![image](https://user-images.githubusercontent.com/61830624/88929825-efd86200-d27a-11ea-8eb4-0148a9107cf8.png)

Go to Auto scaling Groups
![image](https://user-images.githubusercontent.com/61830624/88929996-2ada9580-d27b-11ea-9932-c97ce9338034.png)

Create Auto Scaling group
![image](https://user-images.githubusercontent.com/61830624/88930081-480f6400-d27b-11ea-8005-8a59f4623945.png)

Give a name and switch to launch configuration, select Launch Configuration S20
![image](https://user-images.githubusercontent.com/61830624/88930220-79882f80-d27b-11ea-832e-3052fa20a08f.png)

Select default VPC and 1 or 2 subnets
![image](https://user-images.githubusercontent.com/61830624/88930471-d1bf3180-d27b-11ea-9806-012ec2af78af.png)

Configure group size and scaling policies
![image](https://user-images.githubusercontent.com/61830624/88930621-00d5a300-d27c-11ea-8fc2-502e6129a8fe.png)

Click on Create Auto Scaling group, you will be redirected to the autoscaling group
Now there are 2 new running instances
![image](https://user-images.githubusercontent.com/61830624/88931065-a12bc780-d27c-11ea-99b2-f1fbd61a896b.png)

Successfully created an autoscaling group with a policy to a minimum of 2 and maximum of 2 instances

### Test Auto Scaling Group
- For testing the auto scaling policy, go to the EC2 instance list and select one of your instances.
![image](https://user-images.githubusercontent.com/61830624/88931617-5b233380-d27d-11ea-992e-9a983f5b2a2d.png)

- Go to Actions menu and select Instance State and Select Stop
![image](https://user-images.githubusercontent.com/61830624/88931711-78f09880-d27d-11ea-89f6-ce22b5c33db1.png)

This will stop the instance
![image](https://user-images.githubusercontent.com/61830624/88931852-a76e7380-d27d-11ea-8bed-dea33ad06f65.png)

Once your instance is stopped(after 1-2 minutes) you can see that your stopped instance will be terminating automatically, and a new instance will be launched to fulfill the policy condition.
![image](https://user-images.githubusercontent.com/61830624/88932018-d1279a80-d27d-11ea-9fa3-faac9126c749.png)

Stopped  both instances
![image](https://user-images.githubusercontent.com/61830624/88932406-501cd300-d27e-11ea-8ee9-fd0b6832c053.png)

After the stopped instances are terminated automatically and 2 new instances has been launched
![image](https://user-images.githubusercontent.com/61830624/88932676-b0ac1000-d27e-11ea-9f1a-c4e5f46dd461.png)
