# Running Fooocus (image generation UI) in AWS

---
I used g4 instance with 4 vCpu's. It's the most basic instance with GPU's available. Cost is roughly 0.6 $ per hour.

!!! To use g4 instance you probably have to request a quota increase from 0 to 4 for this type of instance.
To do this, after registering an account and attaching the payment details search for service quotas:

![img_19.png](img_19.png)

Then in dashboard find Amazon Elastic Compute Cloud:

![img_20.png](img_20.png)

Then find and click on All G and VT instances

![img_21.png](img_21.png)

Then click on request increase at account-level 

![img_22.png](img_22.png)

After that choose 4

![img_23.png](img_23.png)

Now wait for a while (up to one day). If they decline you can contact support via the link that will come to your email attached to the request. State the adequate use case and they will almost surely approve.

---

# Running an instance with Gradio on AWS

1. Register on AWS (Make sure to add a default payment method in payment preferences)


2. Install PuTTY (SHH client for Windows): https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html


3. Once you have set up AWS account find EC2 in services:

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

9. Name it as you wish and select rsa and .ppk. Once you click create the download of ppk will begin.

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

15. Now go to the instances tab and click on your instance:

![img_13.png](img_13.png)

16. Find your public IPv4 DNS:

![img_14.png](img_14.png)

17. Your instance name to use to connect in PuTTY will be: ec2-user@[your public DNS]


18. Open PuTTY


19. In category tab find Credentials and attach your private key generated in the step 8:

![img_17.png](img_17.png)

20. Now click on session, paste your instance name (as in step 17) and click open

![img_24.png](img_24.png)

21. Here click accept:

![img_15.png](img_15.png)

22. Congratulations! You are connected to your instance:

![img_16.png](img_16.png)

23. Now run the following commands in terminal one by one:

```
git clone https://github.com/lllyasviel/Fooocus.git
cd Fooocus
pip3 install -r requirements_versions.txt
python3 entry_with_update.py --listen --share
```

24. Now your fooocus instance is publicly running on address indicated in the terminal

![img_18.png](img_18.png)

