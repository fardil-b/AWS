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


