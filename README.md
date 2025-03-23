# cloud-services-models

#1 Identify IaaS, PaaS, SaaS Examples (Daily Interactions)
Problem = Students often struggle to map abstract cloud models to real-world services.
Solution =  Provide relatable examples from daily life.
Examples Table:

Model ||   Example              || Explanation 
IaaS  ||  AWS EC2, DigitalOcean ||   Rent virtual servers to host apps/websites
PaaS	|| Heroku, Google App Engine || Deploy apps without managing servers/networking
SaaS	|| Google Workspace, Slack  || Use ready-to-go software via the internet.
Tip: Encourage students to think of tools they use daily (e.g., Netflix = SaaS, GitHub Codespaces = PaaS).

#2 Research Two Major Cloud Providers
Task: Compare AWS and Google Cloud Platform (GCP).

## AWS Offerings 
- IaaS: EC2 (Virtual Machines), S3 (Storage)  
- PaaS: Elastic Beanstalk, Lambda (Serverless)  
- SaaS: Amazon Chime, QuickSight  

## GCP Offerings
- IaaS: Compute Engine, Cloud Storage  
- PaaS: App Engine, Cloud Functions  
- SaaS: Google Workspace, Apigee API Management

  #3 Managed Service Setup
  - Chosen Platform: AWS Elastic Beanstalk  
- Steps:
- Login to my AWS.
- Navigate to Elastic Beanstalk & click on Create Application.
- I used a demo template for this environment.
- I created a new Key Pair & new EC2
- I configured my Environment (Auto-scaling, load balancing).

Deploy → Capture screenshots of the dashboard and URL.
  ![image](https://github.com/user-attachments/assets/48f218e5-919b-4542-b7cd-f68a9430e7fa)
  ![image](https://github.com/user-attachments/assets/3f081562-6562-4e67-8887-98907cdfb0b3)
  ![image](https://github.com/user-attachments/assets/39603bf8-992f-4cb3-966b-278b87bc39a0)
  ![image](https://github.com/user-attachments/assets/5ec21745-3ddf-4b67-b618-905de81011ef)
  ![image](https://github.com/user-attachments/assets/52edbb79-d39a-4606-a7f4-ddfea730f38d)
![image](https://github.com/user-attachments/assets/6893edc1-9553-42bc-8896-64b0f3b63063)

My environment failed! 
Error Message: *The instance profile aws-elasticbeanstalk-ec2-role associated with the environment does not exist.*
![image](https://github.com/user-attachments/assets/56cc6fb0-16e1-40c9-80bc-15653b7df1d6)



# Troubleshooting
## 4. Environment Failure Analysis  

### Issue Description
The instance profile aws-elasticbeanstalk-ec2-role associated with the environment does not exist.

Troubleshooting: "Instance Profile Does Not Exist" Error  


### Diagnosis  
- Elastic Beanstalk requires the IAM role `aws-elasticbeanstalk-ec2-role` to launch EC2 instances.  
- This role was missing in the AWS account.  

### Resolution  
1. I created the IAM role** with the exact name `aws-elasticbeanstalk-ec2-rolee`. 
2. Attached AWS-managed policies for Elastic Beanstalk permissions.  
3. Updated the environment configuration to use the new role.  

### Screenshots 
- IAM Role Creation:![image](https://github.com/user-attachments/assets/c87d9ddf-f7f8-4bea-b74c-bad99710c688)

- Environment succes Update:![image](https://github.com/user-attachments/assets/4b833a8d-f291-4e88-9366-1d7e04c3c82e)
- My Final Environment:![image](https://github.com/user-attachments/assets/cfd3d816-b90a-4b74-90c7-c855bd50ee1c)

 
# Key Takeaways
Why IAM Roles Matter: Elastic Beanstalk uses roles to grant EC2 instances permissions to interact with AWS services.

Best Practice: Always verify IAM roles exist before deploying environments. Use AWS’s managed policies to avoid permission issues.


