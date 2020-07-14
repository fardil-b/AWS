# Elastic Load Balancing (ELB)- 
- Elastic Load Balancing automatically distributes incoming application traffic across multiple Amazon EC2 instances in the cloud. In this lab, we will demonstrate elastic load balancing with 2 EC2 Instances.

ELB supports 3 types of load balancers:
* Application Load Balancers
* Network Load Balancers
* Classic Load Balancers
![image](https://user-images.githubusercontent.com/61830624/87482182-2b471f80-c631-11ea-9324-3b05108de980.png)

Each load balancer is configured differently.

For Application and Network Load Balancers, you register targets in target groups and route traffic to target groups.

For Classic Load Balancers, you register instances with the load balancer.

# APPLICATION LOAD BALANCER (ALB)
![image](https://user-images.githubusercontent.com/61830624/87476243-59733200-c626-11ea-9858-0d342ea64f01.png)

Go to AWS console, EC2 and Create 4 Instances 2 for images and 2 for videos
![image](https://user-images.githubusercontent.com/61830624/87473402-a3a5e480-c621-11ea-9806-92f55d8ea1d9.png)
Advanced settings,paste the content for our scripts
![image](https://user-images.githubusercontent.com/61830624/87473697-2c248500-c622-11ea-8461-3e7be7059ccf.png)

For the frist script, downloading appache and dispplay message
![image](https://user-images.githubusercontent.com/61830624/87475322-d8676b00-c624-11ea-969e-25a934bbff7e.png)
Second instance-image server 2 script
![image](https://user-images.githubusercontent.com/61830624/87475755-9be83f00-c625-11ea-8811-1d4f525e2d88.png)
3rd instance -video server 1
![image](https://user-images.githubusercontent.com/61830624/87475880-ce923780-c625-11ea-93ac-5e1effb52c7f.png)
4th instance -video server 2
![image](https://user-images.githubusercontent.com/61830624/87475984-f5e90480-c625-11ea-9b70-4f585dfb1276.png)
The 4 instances are created
![image](https://user-images.githubusercontent.com/61830624/87476097-1f099500-c626-11ea-8940-6ac9f4545c0b.png)

Create the Target group for image server
![image](https://user-images.githubusercontent.com/61830624/87477156-f1bde680-c627-11ea-82a1-4b94e4b9c536.png)
![image](https://user-images.githubusercontent.com/61830624/87477217-0f8b4b80-c628-11ea-9efb-6702ba482225.png)
![image](https://user-images.githubusercontent.com/61830624/87477253-1f0a9480-c628-11ea-8b59-369d1d842b29.png)

Register the 2 image procesing server instances to the target group
![image](https://user-images.githubusercontent.com/61830624/87477612-aeb04300-c628-11ea-9661-2dd836cfaa57.png)

Create Target group for video server
![image](https://user-images.githubusercontent.com/61830624/87478025-63e2fb00-c629-11ea-8d64-a7367ce6a427.png)

Now let configure our load balancer
![image](https://user-images.githubusercontent.com/61830624/87478123-8d038b80-c629-11ea-818c-72256bf9a6fa.png)
![image](https://user-images.githubusercontent.com/61830624/87478165-98ef4d80-c629-11ea-8532-5eea5b67f564.png)
![image](https://user-images.githubusercontent.com/61830624/87478319-e10e7000-c629-11ea-9bcc-f46eba4cf680.png)
![image](https://user-images.githubusercontent.com/61830624/87478525-35195480-c62a-11ea-889d-833a5ace5a8c.png)

Let insert our rule 1
![image](https://user-images.githubusercontent.com/61830624/87478881-c7b9f380-c62a-11ea-931d-16363cdb1937.png)
![image](https://user-images.githubusercontent.com/61830624/87478763-97725500-c62a-11ea-8215-39b5b73bebe9.png)
![image](https://user-images.githubusercontent.com/61830624/87479117-30a16b80-c62b-11ea-84f4-fd107e61838e.png)

Rule 2
![image](https://user-images.githubusercontent.com/61830624/87479329-9857b680-c62b-11ea-9084-8774b3b570d8.png)
![image](https://user-images.githubusercontent.com/61830624/87479412-bb826600-c62b-11ea-943f-eb47f367da4d.png)

![image](https://user-images.githubusercontent.com/61830624/87479550-fdaba780-c62b-11ea-9620-9ea787a542c2.png)

Instances working as expected
![image](https://user-images.githubusercontent.com/61830624/87480062-e0c3a400-c62c-11ea-8a5f-4b24efe7d7e8.png)
![image](https://user-images.githubusercontent.com/61830624/87479910-9e01cc00-c62c-11ea-853f-426bd5767d4e.png)

Copy the DNS Name from load balancers and paste in your internet browser
![image](https://user-images.githubusercontent.com/61830624/87480267-431ca480-c62d-11ea-9c5d-69bbb60e2eb6.png)
![image](https://user-images.githubusercontent.com/61830624/87480410-8f67e480-c62d-11ea-89f6-8fbadb8c8ab6.png)
Traffic goes to images server 1 and 2 
![image](https://user-images.githubusercontent.com/61830624/87480453-a7d7ff00-c62d-11ea-8d2a-7bbc55d9ea65.png)
![image](https://user-images.githubusercontent.com/61830624/87480509-c0481980-c62d-11ea-9c0b-60817c94789d.png)

If we change the request to /videos.html 
![image](https://user-images.githubusercontent.com/61830624/87480661-14eb9480-c62e-11ea-8c8c-b596ea29a9ed.png)
![image](https://user-images.githubusercontent.com/61830624/87480681-20d75680-c62e-11ea-9655-4f54c9617a88.png)

To make sure the load balancer is working, let's make some chnages to the rule
![image](https://user-images.githubusercontent.com/61830624/87481015-cab6e300-c62e-11ea-974b-1c9be7b424d5.png)
![image](https://user-images.githubusercontent.com/61830624/87480936-a2c77f80-c62e-11ea-9816-440d898f3102.png)
![image](https://user-images.githubusercontent.com/61830624/87481140-0b166100-c62f-11ea-836d-194acecc971b.png)
![image](https://user-images.githubusercontent.com/61830624/87481219-36994b80-c62f-11ea-8727-9839e23e59ea.png)
![image](https://user-images.githubusercontent.com/61830624/87481381-7eb86e00-c62f-11ea-8adc-440a7a0fe8bb.png)

 Now we see that the request is going to the home page of the **video** processing servers rather than **image** processing servers










