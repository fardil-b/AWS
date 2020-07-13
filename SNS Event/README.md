# Creating and Subscribing to SNS Topics

## What is SNS?
* SNS stands for Simple Notification Service.
* Provides a low-cost infrastructure for the mass delivery of messages, predominantly to mobile users.
* SNS acts as a single message bus that can message to a variety of devices and platforms.
* SNS uses the publish/subscribe model for push delivery of messages.
* SNS enables us to decouple microservices, distributed systems, and serverless applications using fully managed pub/sub.
* Publishers communicate asynchronously with subscribers by producing and sending a message to a topic, which is a logical access point and communication channel.
* Subscribers i.e., web servers, email addresses, SQS queues etc., consume or receive the message or notification over one of the supported protocols when they are subscribed to the topic.
* Recipients subscribe to one or more "topics" within SNS.
* Using SNS topics, the publisher systems can fan out messages to a large number of subscriber endpoints for parallel processing, including Amazon SQS queues, AWS Lambda functions, and HTTP/S webhooks.
* SNS is reliable in delivering messages with durability.
* SNS can help in automatically scale the workload.
* Using topic policies, you can keep messages private and secure.


Go to AES Console and SNS
![image](https://user-images.githubusercontent.com/61830624/87314592-c18d1f80-c523-11ea-959a-d75576aeb402.png)
Create SNS Topics
![image](https://user-images.githubusercontent.com/61830624/87314903-1d57a880-c524-11ea-9716-77436a65baa9.png)

We dont't have any subscribers, so we create a subcription
![image](https://user-images.githubusercontent.com/61830624/87315600-e5049a00-c524-11ea-805a-8fa3e871b2f9.png)

you should have received an email asking for comfirmation 
![image](https://user-images.githubusercontent.com/61830624/87315762-1aa98300-c525-11ea-853e-2a248dcdf9a4.png)

Once  confirm you should get this message
![image](https://user-images.githubusercontent.com/61830624/87315893-49275e00-c525-11ea-8686-cbeb4691ec3d.png)

Back in SNS, Refresh your console, subscription is set
![image](https://user-images.githubusercontent.com/61830624/87316043-825fce00-c525-11ea-9609-3b6f8b65ec5b.png)

Put eveyone in topic policy
![image](https://user-images.githubusercontent.com/61830624/87316816-89d3a700-c526-11ea-94e4-8d839e46b0af.png)

Copy your **ARN** then go to S3
![image](https://user-images.githubusercontent.com/61830624/87317335-27c77180-c527-11ea-9a51-ada75dfaca9d.png)



