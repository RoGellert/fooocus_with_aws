# Running Fooocus (image generation UI) in AWS



1. Register on AWS (Make sure to add a default payment method in payment preferences)


2. Install PuTTY (SHH client for Windows): https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html


3. Once you have AWS find EC2 in services:

![img.png](img.png)

4. From EC2 dashboard click launch an instance:

![img_1.png](img_1.png)

5. Name your instance as you wish:

![img_2.png](img_2.png)

6. In the Amazon Machine Image (AMI) choose the following:

![img_3.png](img_3.png)

7. In instance type select (g4dn.xlarge)

![img_4.png](img_4.png)

8. In key pair section click create key pair:

![img_6.png](img_6.png)

9. Name in as you wish and select rsa and .ppk. Once you click create the download of ppk will begin.

![img_5.png](img_5.png)

10. Select the key: 

![img_7.png](img_7.png)

11. If you want to make it secure you can allow only certain IP's to connect to an istance, but to make it simpler I'll
skip this part

![img_8.png](img_8.png)

12. In the storage section select as much as you need, 128 would be a reasonable choice

![img_10.png](img_10.png)

13. Then in summary click launch instance:

![img_11.png](img_11.png)

14. Congratulations! Your instance is running!

15. Now go to the instances tab:

![img_12.png](img_12.png)
