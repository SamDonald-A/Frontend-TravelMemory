**Deploying MERN Application on AWS**

Useful Links:

GitHub -
[[https://github.com/SamDonald-A/TravelMemory]{.underline}](https://github.com/SamDonald-A/TravelMemory)

Frontend -
<https://github.com/SamDonald-A/Frontend-TravelMemory/tree/master>

Backend -
<https://github.com/SamDonald-A/backend-travelmemory/tree/master>

<img width="796" height="1030" alt="image" src="https://github.com/user-attachments/assets/83170765-0a07-48c1-bc97-d57fddeb8144" />


**Frontend Configuration**

*Repeat the initial steps that are same as backend instance*

**\
Step 1: Creating a new Frontend instance and connecting to it via SSH
using the instance\'s DNS address.**

**Step 2: Installing GitHub in Frontend Instance**

**Step 3: Copy the link from GitHub and clone it in the frontend
Instance**

**Step 4: Setup *url.js* which is in frontend \> src folder and copy the
backend URL which is a DNS name link from the Backend Load Balancer and
replace the baseUrl variable**

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image2.png){width="6.5in"
height="0.8826388888888889in"}

**Step 6: Install Nodejs in the frontend**

**Step 7: Install npm for your frontend node modules**

**Step 8: Check frontend on browser using DNS link or Public IP**

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image3.jpeg){width="4.852174103237095in"
height="1.5215277777777778in"}

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image4.jpeg){width="5.9021981627296585in"
height="2.9826082677165355in"}

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image5.jpeg){width="6.504166666666666in"
height="3.2868055555555555in"}

**Step 9: Create Build from the frontend file and copy the build file to
the Nginx server**

\# To create build file from frontend\
npm run build

sudo cp -r /home/ec2-user/TravelMemory/frontend/build/\*
/usr/share/nginx/html/

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image6.png){width="6.5in"
height="3.245138888888889in"}

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image7.png){width="6.5in"
height="0.8972222222222223in"}

\# To copy build file from frontend to Nginx server

sudo cp -r /home/ec2-user/TravelMemory/frontend/build/\*
/usr/share/nginx/html/

\# Restart the nginx server

sudo systemctl restart nginx

-   Now the front should be running and able to see that on the browser
    > using DNS link

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image8.jpeg){width="5.508889982502187in"
height="2.791304680664917in"}

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image9.png){width="5.528720472440945in"
height="2.823428477690289in"}

**Step 10: Stop the instance and create AMI -- Amazon Machine Image from
EC2 console**

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image10.jpeg){width="5.965217629046369in"
height="3.0386559492563427in"}

**Step 11: Create Two EC2 Instances using AMI -- These two for scaling &
Load distribution**

-   Change the one of the Instance front end header names to see Load
    > balancer distributing traffic to each Frontends

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image11.png){width="6.5in"
height="0.33055555555555555in"}

**Step 12: Create target group for Load Balancer**

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image12.png){width="6.2021544181977255in"
height="2.8930139982502188in"}

**Step 13: Create Load Balancer using the backend target goup and copy
the DNS link to see frontend is running**

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image13.jpeg){width="6.495833333333334in"
height="2.5131944444444443in"}

Now, the Frontend Part is created successfully

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image14.png){width="2.4065857392825896in"
height="4.479792213473316in"}

**Domain Setup**

**Step 14: Now copy this Link and configure the domain service provider\
**

-   My case I am using Hostinger -- select domain name and go to DNS
    > settings

-   Add CNAME record and past the frontend Load balancer DNS link in the
    > value input

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image15.jpeg){width="6.504166666666666in"
height="3.2784722222222222in"}

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image16.jpeg){width="6.504166666666666in"
height="3.338888888888889in"}

-   We can check the DNS update live using 3^rd^ party websites
    > [www.dnschecker.org](http://www.dnschecker.org)

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image17.jpeg){width="6.504166666666666in"
height="3.2868055555555555in"}

-   And now the website should be visible after DNS updated

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image18.jpeg){width="6.504166666666666in"
height="3.338888888888889in"}

-   Check adding new trip

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image19.jpeg){width="6.5in"
height="3.302049431321085in"}

-   Viewing the new trip that added

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image20.jpeg){width="6.504166666666666in"
height="3.321527777777778in"}

In each screen shot of window we see that the Load balancer is
distributing the traffic by each request to different Instances.

The Application is running successfully with Front and Backend Load
Balancers.

![](vertopal_43b094cb227a4f8ca21b52429b8ee97b/media/image21.jpeg){width="5.513043525809274in"
height="7.1367814960629925in"}

Documentation by: Sam Donald A\
Email: <samdonaldand@gmail.com>

GitHub: <https://github.com/SamDonald-A>

Website: www.samdonald.in
