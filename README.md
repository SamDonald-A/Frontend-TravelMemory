**Deploying MERN Application on AWS**

Useful Links:

GitHub -
[[https://github.com/SamDonald-A/TravelMemory]{.underline}](https://github.com/SamDonald-A/TravelMemory)

Frontend -
<https://github.com/SamDonald-A/Frontend-TravelMemory/tree/master>

Backend -
<https://github.com/SamDonald-A/backend-travelmemory/tree/master>

<img width="770" height="930" alt="image" src="https://github.com/user-attachments/assets/83170765-0a07-48c1-bc97-d57fddeb8144" />


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

<img width="975" height="132" alt="image" src="https://github.com/user-attachments/assets/c8c34b0d-65a6-47a6-bd9f-0d8ccae15da6" />


**Step 6: Install Nodejs in the frontend**

**Step 7: Install npm for your frontend node modules**

**Step 8: Check frontend on browser using DNS link or Public IP**

<img width="728" height="228" alt="image" src="https://github.com/user-attachments/assets/5deb8625-258b-432f-a39b-409d89f19658" />


<img width="885" height="447" alt="image" src="https://github.com/user-attachments/assets/d3b9a877-bf7e-44b8-afa1-825eb5e6d904" />


<img width="976" height="493" alt="image" src="https://github.com/user-attachments/assets/591961be-c2e1-4353-b202-be7a239f771f" />


**Step 9: Create Build from the frontend file and copy the build file to
the Nginx server**

\# To create build file from frontend\
npm run build

sudo cp -r /home/ec2-user/TravelMemory/frontend/build/\*
/usr/share/nginx/html/

<img width="975" height="487" alt="image" src="https://github.com/user-attachments/assets/1f7ed360-3873-4b9d-9e6d-9a8b538319be" />


<img width="826" height="419" alt="image" src="https://github.com/user-attachments/assets/78cc6a18-8f44-48f6-9ada-1e8cbf27cf32" />


\# To copy build file from frontend to Nginx server

sudo cp -r /home/ec2-user/TravelMemory/frontend/build/\*
/usr/share/nginx/html/

\# Restart the nginx server

sudo systemctl restart nginx

-   Now the front should be running and able to see that on the browser
    > using DNS link

<img width="975" height="135" alt="image" src="https://github.com/user-attachments/assets/fd027bd1-187c-4e3e-93bb-5f0cb9b533ac" />


<img width="828" height="423" alt="image" src="https://github.com/user-attachments/assets/3fc60b0c-a576-461c-8c6f-590d6d9aec4c" />


**Step 10: Stop the instance and create AMI -- Amazon Machine Image from
EC2 console**

<img width="895" height="456" alt="image" src="https://github.com/user-attachments/assets/8a134c1c-7d55-4d04-9800-918201666c19" />


**Step 11: Create Two EC2 Instances using AMI -- These two for scaling &
Load distribution**

-   Change the one of the Instance front end header names to see Load
    > balancer distributing traffic to each Frontends

<img width="975" height="50" alt="image" src="https://github.com/user-attachments/assets/c7548748-3cd1-47d8-b62a-ddb9aea776e7" />


**Step 12: Create target group for Load Balancer**

<img width="930" height="434" alt="image" src="https://github.com/user-attachments/assets/78401b3a-399f-4fda-8c34-7269c616bb9d" />


**Step 13: Create Load Balancer using the backend target goup and copy
the DNS link to see frontend is running**

<img width="974" height="377" alt="image" src="https://github.com/user-attachments/assets/22deba75-0d4a-45b3-b0f0-7808f9e33bdf" />


Now, the Frontend Part is created successfully

<img width="361" height="672" alt="image" src="https://github.com/user-attachments/assets/e86be2f6-35ec-4b68-a2b6-e69742847891" />


**Domain Setup**

**Step 14: Now copy this Link and configure the domain service provider\
**

-   My case I am using Hostinger -- select domain name and go to DNS
    > settings

-   Add CNAME record and past the frontend Load balancer DNS link in the
    > value input

<img width="976" height="492" alt="image" src="https://github.com/user-attachments/assets/ab4d34bd-b323-4ace-b372-c5be99b2479f" />


<img width="976" height="501" alt="image" src="https://github.com/user-attachments/assets/16db7fea-32a6-48c8-96d3-6e65628b1efc" />


-   We can check the DNS update live using 3^rd^ party websites
    > [www.dnschecker.org](http://www.dnschecker.org)

<img width="976" height="493" alt="image" src="https://github.com/user-attachments/assets/2159fcac-022d-4e73-8ff9-d49bc3d21652" />


-   And now the website should be visible after DNS updated

<img width="976" height="501" alt="image" src="https://github.com/user-attachments/assets/5b92864b-abec-4067-9243-b3c7a2eb6f4e" />


-   Check adding new trip

<img width="975" height="495" alt="image" src="https://github.com/user-attachments/assets/1ea0e387-ea50-4843-a3bb-0ffff011c9dd" />


-   Viewing the new trip that added

<img width="976" height="498" alt="image" src="https://github.com/user-attachments/assets/465e0248-1f2a-41b1-a6e3-a7e0f13f4c12" />


In each screen shot of window we see that the Load balancer is
distributing the traffic by each request to different Instances.

The Application is running successfully with Front and Backend Load
Balancers.

<img width="827" height="1070" alt="image" src="https://github.com/user-attachments/assets/5fe0ed18-b972-4875-bac5-2d66910f7b53" />


Documentation by: Sam Donald A\
Email: <samdonaldand@gmail.com>

GitHub: <https://github.com/SamDonald-A>

Website: www.samdonald.in
