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

### **Issue Description**  
[Briefly describe the failure, e.g., "Deployment to AWS Elastic Beanstalk failed due to misconfigured IAM roles."]  

### **Diagnostic Steps**  
1. **Error Message:**  
 **Logs Reviewed:**  
- AWS CloudWatch Logs  
- Elastic Beanstalk Environment Health Dashboard  
3. **Configuration Checks:**  
- Verified IAM user permissions for Elastic Beanstalk.  
- Validated `app.yaml` syntax for GCP App Engine.  

### **Root Cause**  
- **AWS:** Missing `elasticbeanstalk:CreateApplication` permission in IAM policy.  
- **GCP:** Billing account not linked to the project, blocking resource provisioning.  

### **Resolution**  
- **AWS:** Attached the `AWSElasticBeanstalkFullAccess` policy to the IAM user.  
- **GCP:** Linked an active billing account to the project via GCP Console.  

### **Screenshots**  
- Include error messages, logs, and post-resolution success screenshots.  
Why This Matters
Learning Objective: Demonstrates problem-solving skills and understanding of cloud platform dependencies (e.g., IAM, billing).

Professional Practice: Mirrors real-world DevOps workflows where debugging is critical.

Adjustments to Presentation.md
Add a slide summarizing the failure:

markdown
Copy
## Lesson 3: Environment Failure & Debugging  

- **Common Pitfalls:**  
  - Permissions (IAM roles, service accounts).  
  - Billing/Quota limitations.  
  - Configuration typos (e.g., `app.yaml`).  
- **Key Takeaway:**  
  - Always check logs first; 90% of issues are permissions or syntax errors!  
Final Repository Structure
