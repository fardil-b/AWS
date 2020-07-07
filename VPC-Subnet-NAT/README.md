# AWS NAT INSTANCE
Use a network address translation (NAT) instance in a public subnet in your VPC to enable instances in the private subnet to initiate 
outbound IPv4 traffic to the internet , but prevent the instances from receiving inbound traffic initiated by someone on the internet.
The steps are:
* step 1 Create VPC
* Step 2 Create two Subnets
* step 3 Attach an internet gateway to the VPC
* step 4 Create a custom route table
* step 5 Launch Instance and create the NATSG
* step 6 PuTTYgen and Putty
* step 7 Ping to google

![image](https://user-images.githubusercontent.com/61830624/86799702-85187a00-c072-11ea-87ba-102f1a0eba44.png)

# Step 1 create VPC
![image](https://user-images.githubusercontent.com/61830624/86818232-67eda680-c086-11ea-8831-428d3cff1d58.png)

# Step 2 create 2 subnets (1 public & 1 private)
![image](https://user-images.githubusercontent.com/61830624/86818640-e8aca280-c086-11ea-8990-d20e796ed777.png)
![image](https://user-images.githubusercontent.com/61830624/86818900-3e814a80-c087-11ea-8a86-7c9fde9af16d.png)

# Step 3 Attach an internet gateway to the VPC
## create IGW
![image](https://user-images.githubusercontent.com/61830624/86819209-9e77f100-c087-11ea-9b00-e50eb44f69f0.png)
## Attache the IGW to VPC
![image](https://user-images.githubusercontent.com/61830624/86819334-c9fadb80-c087-11ea-9e74-42ce85314983.png)

# Step 4 Create a custom route table
## Create a route table
![image](https://user-images.githubusercontent.com/61830624/86819525-0f1f0d80-c088-11ea-9ea6-31b1361dbe70.png)
## Edit the route by adding the IGW
![image](https://user-images.githubusercontent.com/61830624/86819742-5efdd480-c088-11ea-9158-2e86bab0a498.png)
## Edit Subnet associations by adding public subnet
![image](https://user-images.githubusercontent.com/61830624/86819980-b2702280-c088-11ea-8a04-43d0a0a76eb7.png)

# Step 5 Launch Instances and create the NATSG
## Create first instance, chose our vpc, public subnet and Enable public IP
![image](https://user-images.githubusercontent.com/61830624/86820442-5d80dc00-c089-11ea-874f-231ef69af6d0.png)

## Create Security group and add ICMP-IPv4 to be able to ping
![image](https://user-images.githubusercontent.com/61830624/86820950-0e877680-c08a-11ea-90b4-adaf0b46fea4.png)
## Make sure you download **Download Key Pair**
![image](https://user-images.githubusercontent.com/61830624/86821470-bb61f380-c08a-11ea-87b6-ce6121e1d51d.png)

## Create second instance, connect with vpc, private subnet and disable public IP
![image](https://user-images.githubusercontent.com/61830624/86821732-07149d00-c08b-11ea-8156-31bd3811b8ba.png)

## Use existing security group we created (NAT-SG)
![image](https://user-images.githubusercontent.com/61830624/86822215-9f128680-c08b-11ea-89c0-7e69c4bdeab8.png)
![image](https://user-images.githubusercontent.com/61830624/86822481-f9abe280-c08b-11ea-9453-4346a1fd1a76.png)

## Both up and running 
![image](https://user-images.githubusercontent.com/61830624/86823238-e6e5dd80-c08c-11ea-8118-18e9b9e5d1a8.png)

# Step 6 Use PuTTYgen and PuTTY
## Load the key pair in PuTTYgen and put "All files"
![image](https://user-images.githubusercontent.com/61830624/86824557-940d2580-c08e-11ea-903c-d6200d9cf785.png)
## Save private key
![image](https://user-images.githubusercontent.com/61830624/86824256-2f51cb00-c08e-11ea-9207-4328318642e0.png)

## Copy Public IP and go to PuTTY
![image](https://user-images.githubusercontent.com/61830624/86825060-3cbb8500-c08f-11ea-8789-23cbc555903b.png)
## Insert Public IP 
![image](https://user-images.githubusercontent.com/61830624/86825293-7a201280-c08f-11ea-9951-178fbda91ebf.png)
## Go to SSH Auth and Browse the private key we got from PuTTYgen
![image](https://user-images.githubusercontent.com/61830624/86825670-f0247980-c08f-11ea-936a-ca5aea9b0ac1.png)

## Enter user name "ec2-user"
![image](https://user-images.githubusercontent.com/61830624/86826200-b142f380-c090-11ea-90a5-4e9eddf8b542.png)

# Step 7 Ping to internet
![image](https://user-images.githubusercontent.com/61830624/86826632-4f36be00-c091-11ea-8398-1232fd5c0fea.png)
## Copy the content of the key Pair and paste in PuTTY
![image](https://user-images.githubusercontent.com/61830624/86827175-f61b5a00-c091-11ea-954b-9bc436870431.png)
![image](https://user-images.githubusercontent.com/61830624/86827703-a12c1380-c092-11ea-92c1-6cc238a5c1ff.png)

## Get the private IP
![image](https://user-images.githubusercontent.com/61830624/86828124-18fa3e00-c093-11ea-8b33-bee0033ca346.png)
## We are in the private instance but can't access internet (no response when ping)
![image](https://user-images.githubusercontent.com/61830624/86828719-e1d85c80-c093-11ea-9434-342c5a43d81c.png)
Reason: The default route table is not connected to Nat gateway
## Go to Route Table and Add Route and connect to NAt Instance
![image](https://user-images.githubusercontent.com/61830624/86829766-1993d400-c095-11ea-954e-117b4c703d63.png)
## Still does not ping
![image](https://user-images.githubusercontent.com/61830624/86829996-61b2f680-c095-11ea-946b-2d0fc5907620.png)

## Go to Public instance, Action, Networking and change source/Destination Check "Disable"
![image](https://user-images.githubusercontent.com/61830624/86830365-e43bb600-c095-11ea-8206-007794b8a924.png)
![image](https://user-images.githubusercontent.com/61830624/86830191-ae96cd00-c095-11ea-965b-5f1d100ca878.png)

# Now it's working 
![image](https://user-images.githubusercontent.com/61830624/86830689-485e7a00-c096-11ea-9b0d-b1fac2b01c0c.png)








