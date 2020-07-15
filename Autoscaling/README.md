# Simple Autoscaling demonstration

![image](https://user-images.githubusercontent.com/61830624/87487611-6c91fc00-c63e-11ea-84df-63370bf68fc6.png)
Click __create launch configuration__
![image](https://user-images.githubusercontent.com/61830624/87487651-86334380-c63e-11ea-838a-62acafaeb5a5.png)
![image](https://user-images.githubusercontent.com/61830624/87487812-f9d55080-c63e-11ea-8907-004c3fd5ba62.png)
click **create auto scaling group**
![image](https://user-images.githubusercontent.com/61830624/87487944-55074300-c63f-11ea-96d9-3d97839d0690.png)
![image](https://user-images.githubusercontent.com/61830624/87488157-eaa2d280-c63f-11ea-9441-5e604ee32bbd.png)
![image](https://user-images.githubusercontent.com/61830624/87488219-1a51da80-c640-11ea-8622-a41526cf3af9.png)
![image](https://user-images.githubusercontent.com/61830624/87488350-6ef55580-c640-11ea-9a36-25c134bb0f85.png)
All in healthy state
![image](https://user-images.githubusercontent.com/61830624/87488399-8e8c7e00-c640-11ea-8a84-8812907dfdcf.png)
Let's make one unhealthy
![image](https://user-images.githubusercontent.com/61830624/87488486-cc89a200-c640-11ea-9a57-afd07bdcebe3.png)
![image](https://user-images.githubusercontent.com/61830624/87488552-fc38aa00-c640-11ea-93af-b9c2564e9140.png)
Autoscaling has terminated the server we have stopped and it has now provision one more autoscaling server
![image](https://user-images.githubusercontent.com/61830624/87488732-65202200-c641-11ea-88c7-ac32595b7e89.png)
It has successfully replace an unhealthy instance with a healthy one and it has maintain an equal number of instances across the 2 AZs
![image](https://user-images.githubusercontent.com/61830624/87488873-c647f580-c641-11ea-8f1d-b416d9641dda.png)

