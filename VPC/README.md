# Creating a VPC
### First from Amazon consle go VPC, then your VPC
![image](https://user-images.githubusercontent.com/61830624/86521705-8c623c80-be54-11ea-821f-482f3e6e52cb.png)

### Next "Create VPC"
![image](https://user-images.githubusercontent.com/61830624/86521948-3d69d680-be57-11ea-8673-1c3566c71c96.png)

### Give it a name, Select a CIDR Block and  Click on "create"
![image](https://user-images.githubusercontent.com/61830624/86521924-df3cf380-be56-11ea-8710-27baa90ada70.png)

### VPC has been created
![image](https://user-images.githubusercontent.com/61830624/86521906-b157af00-be56-11ea-83e2-952fc637dfd6.png)

# Now let's launch our subnet inside this VPC
### First create 2 subnets: one for private and another for public
![image](https://user-images.githubusercontent.com/61830624/86522163-182a9780-be5a-11ea-8740-e84893bc57de.png)

### Fill the required info: Name, VPC, AZ & CIDR block
![image](https://user-images.githubusercontent.com/61830624/86522211-cf271300-be5a-11ea-81e8-290618d2ed8f.png)

### Repeat the same procedure for second subnet and name it as private
![image](https://user-images.githubusercontent.com/61830624/86522246-3fce2f80-be5b-11ea-8f0f-20e36811cea3.png)

### Create a Network Acess Control List
#### A network access control list (ACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets.
* Select a name for your ACL
* Select your VPC
![image](https://user-images.githubusercontent.com/61830624/86530678-f6153180-beba-11ea-83e8-b58f05502aa4.png)

### Here you will have the option to associatw the subnet as well as define the rule for this Network ACL
![image](https://user-images.githubusercontent.com/61830624/86530822-59ec2a00-bebc-11ea-83d2-04cd90701196.png)

### First let's associate the subnet and select Public subnet
![image](https://user-images.githubusercontent.com/61830624/86531258-fbc14600-bebf-11ea-8760-1e88ebc2bc7f.png)

### Then go to "Inbound Rules", "Edit inbound Rules" and ADD Rule
![image](https://user-images.githubusercontent.com/61830624/86535747-eb6e9280-bee2-11ea-95f3-ffb88255de8d.png)

### We do the same for outbound
![image](https://user-images.githubusercontent.com/61830624/86535775-1ce75e00-bee3-11ea-9e4a-9921a6a9029c.png)

### Now we create the Private Network ACL
![image](https://user-images.githubusercontent.com/61830624/86535860-94b58880-bee3-11ea-8a38-fbf975b601f9.png)

### Accociate the subnet with private subnet
![image](https://user-images.githubusercontent.com/61830624/86535895-dba37e00-bee3-11ea-90cf-202cfb35905e.png)

### Add Inbound and outbound Rules
![image](https://user-images.githubusercontent.com/61830624/86535936-19080b80-bee4-11ea-9f23-e69f3dde6b24.png)
![image](https://user-images.githubusercontent.com/61830624/86535990-887dfb00-bee4-11ea-81b0-1017b6c05bc9.png)

### Next step is to create the Internet gateway (IGW) so that we can access the internet
![image](https://user-images.githubusercontent.com/61830624/86536111-5b7e1800-bee5-11ea-8fc8-4f773dc2532f.png)

### Attach IGW to VPC
![image](https://user-images.githubusercontent.com/61830624/86536160-badc2800-bee5-11ea-8ffd-891b2a439b1d.png)

## Next step is to create a public Route table
### So we create a route table
![image](https://user-images.githubusercontent.com/61830624/86536252-5e2d3d00-bee6-11ea-8211-96696478f8b4.png)

### Let asssociate it with the public subnet
![image](https://user-images.githubusercontent.com/61830624/86538541-d8fe5400-bef6-11ea-9937-df6de9e18864.png)

### Next we define the route, it already has a local that is connected to the VPC we need to add another to connect to the IGW
![image](https://user-images.githubusercontent.com/61830624/86538771-58d8ee00-bef8-11ea-8e12-ac23b77b7e3c.png)

### Next create a route table for the private
![image](https://user-images.githubusercontent.com/61830624/86538867-e87e9c80-bef8-11ea-81a6-d07fed4caf0d.png)

### Associate the private subnet
![image](https://user-images.githubusercontent.com/61830624/86538897-4317f880-bef9-11ea-822d-6493d53f5f90.png)

### For private route table, the table entry should be the local route, so we keep it as it is

# Next step is to launch the instances
## Go to EC2, Launch Instance 
![image](https://user-images.githubusercontent.com/61830624/86539108-6db68100-befa-11ea-8579-73f56fd6dcfe.png)

## Select the AMI
![image](https://user-images.githubusercontent.com/61830624/86539140-a22a3d00-befa-11ea-9ad5-0bf00f246d3a.png)

![image](https://user-images.githubusercontent.com/61830624/86539168-cede5480-befa-11ea-9053-add30460a33e.png)

## Next configure Instance Details
#### Enable- Auto Assign public Ip (Requests a public IP address from Amazon's public IP address pool, to make your instance reachable from the Internet)
![image](https://user-images.githubusercontent.com/61830624/86539385-5e383780-befc-11ea-87a8-9dc1366f821d.png)

### Add Storage
![image](https://user-images.githubusercontent.com/61830624/86539433-950e4d80-befc-11ea-91ab-739620103557.png)

### Add tag, you can name it Public Webserver
![image](https://user-images.githubusercontent.com/61830624/86539478-ed454f80-befc-11ea-8b0e-d6f47a61bd27.png)

### You can create a new security group
![image](https://user-images.githubusercontent.com/61830624/86539510-37c6cc00-befd-11ea-8e73-ee7d7a0cb655.png)

### Select review and launch
![image](https://user-images.githubusercontent.com/61830624/86539523-66dd3d80-befd-11ea-907a-d4adea8d8d78.png)
![image](https://user-images.githubusercontent.com/61830624/86539544-a572f800-befd-11ea-8f0e-3ba020231a1b.png)

![image](https://user-images.githubusercontent.com/61830624/86539564-e10dc200-befd-11ea-8418-0a162e95d958.png)
![image](https://user-images.githubusercontent.com/61830624/86539583-000c5400-befe-11ea-819a-902f3e333eb7.png)

### Now let launch an instances for our private subnet
#### make sure "Auto-assign Public IP" is disable
![image](https://user-images.githubusercontent.com/61830624/86539617-4b266700-befe-11ea-95e6-598e564fc01e.png)
###Add storage and Tags
![image](https://user-images.githubusercontent.com/61830624/86539638-84f76d80-befe-11ea-8587-ca2155ffaa5b.png)
![image](https://user-images.githubusercontent.com/61830624/86539658-a5272c80-befe-11ea-96a6-f8600f3cc9ce.png)

### Select existing secuity group
![image](https://user-images.githubusercontent.com/61830624/86539744-575ef400-beff-11ea-8c97-d78267896405.png)
### Review and Launch
![image](https://user-images.githubusercontent.com/61830624/86539785-9c832600-beff-11ea-836a-fa6eb6430a02.png)

## Now let'S check if the public webserver can asses the internet or not
Convert your private key using PuTTYgen
Locate the private key (.pem file) for the key pair that you specified when you launched the instance. Convert the .pem file to a .ppk file for use with PuTTY
![image](https://user-images.githubusercontent.com/61830624/86585156-56bd7080-bf86-11ea-927f-6b5a3f9220c0.png)

### We SSH into our public server and use PuTTY
![image](https://user-images.githubusercontent.com/61830624/86539828-11566000-bf00-11ea-97d6-410de4888d41.png)


![image](https://user-images.githubusercontent.com/61830624/86568903-e4d92d00-bf6d-11ea-92d4-5a72d868739e.png)

![image](https://user-images.githubusercontent.com/61830624/86567828-400a2000-bf6c-11ea-8a92-6ba7d786c51c.png)

## Let's see if we can download some update from the internet
### We install the Apache webserver

![image](https://user-images.githubusercontent.com/61830624/86569355-8fe9e680-bf6e-11ea-938d-bf24c2dd4e21.png)
![image](https://user-images.githubusercontent.com/61830624/86569447-b60f8680-bf6e-11ea-8c13-69ec46254579.png)
## You can see that this instance can communicate with the internet and can download the patches from it
### The public webserver is runnig as espected :)

# Now let's SSH in the Private server and see if it can connect to the internet
## We need to SSH into the private server using the  public webserver
### We need to use the public webserver as the Bastion host or jump server
     [iNSERT BASTION PICTURE HERE]
     
### In order to SSH into private server we need the key, which we do not have
## If we try to connect and do the same as for the public server, we get an error message
![image](https://user-images.githubusercontent.com/61830624/86583563-c7af5900-bf83-11ea-8f69-9c3f87db18ec.png)

### For demonstration purposes we are going to create a temporary key, we copy the content of the key and create a new key on the public webserver
![image](https://user-images.githubusercontent.com/61830624/86577894-3cca6080-bf7b-11ea-9beb-c09ce78501b0.png)

## Create a new folder and paste the content of the key here
![image](https://user-images.githubusercontent.com/61830624/86578220-c11ce380-bf7b-11ea-9ea9-6e1bfbd96a8e.png)


![image](https://user-images.githubusercontent.com/61830624/86579842-24a81080-bf7e-11ea-8fce-37fdf7674e80.png)

## Now we hsve SHH into the private server
![image](https://user-images.githubusercontent.com/61830624/86586821-d2b8b800-bf88-11ea-98f0-5d1be9c24a01.png)

### But can it download any updates from the internet
![image](https://user-images.githubusercontent.com/61830624/86586945-101d4580-bf89-11ea-8397-d71024e9e378.png)

#For it to connect to the internet we need to create a NAT instance or NAT Gateway
# Go to YOUR VPC and Create NAT INSTANCE
![image](https://user-images.githubusercontent.com/61830624/86622526-4924dc80-bfc0-11ea-8f88-a23c6b894d6f.png)

# For testing 
Add inbound and outbound rule
![image](https://user-images.githubusercontent.com/61830624/86625343-3d87e480-bfc5-11ea-819e-b858593c577a.png)


Updating main route table
![image](https://user-images.githubusercontent.com/61830624/86624191-3069f600-bfc3-11ea-80e8-a12b6b3a4bdd.png)



# Ping does not work
![image](https://user-images.githubusercontent.com/61830624/86608574-0573a800-bfab-11ea-8269-4d38ecbc8132.png)

# Due to security group
Ping isICMP protocol so we need to add it 
![image](https://user-images.githubusercontent.com/61830624/86608962-82068680-bfab-11ea-8d86-24d0a103ff03.png)


# Now it works :-)
![image](https://user-images.githubusercontent.com/61830624/86609077-b1b58e80-bfab-11ea-9f2d-cd932bd65f1d.png)
