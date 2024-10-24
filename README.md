# AWS Cloud Cost Optimization - Identifying Stale Resources
Created a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

Description: The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

# Create an EC2 instance 
![image](https://github.com/user-attachments/assets/b22f149c-1ee1-4897-aa60-fd1fa06ad257)
