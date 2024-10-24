# AWS Cloud Cost Optimization - Identifying Stale Resources
Created a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

Description: The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if it exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

## Created an EC2 instance 
![image](https://github.com/user-attachments/assets/b22f149c-1ee1-4897-aa60-fd1fa06ad257)

## Created a Snapshot
![image](https://github.com/user-attachments/assets/c1d69f1b-15e7-4697-a1b6-a05a4ad6f230)

## Created a Lambda Function
![image](https://github.com/user-attachments/assets/b90c4603-497f-4637-9304-d9f6594fdce7)

## Allow these permissions using IAM Roles
![image](https://github.com/user-attachments/assets/d3022661-e173-456d-92ee-77a9d85623bd)

## Executed the file "ebs_stale_snapshosts.py" in the code editor 
![image](https://github.com/user-attachments/assets/520fb3a7-8a0a-4b47-99ac-6ba29808f16c)

## Succeeded (At this point, the snapshot won't be deleted because it's still attached to a volume. However, once the instance (and the associated volume) is deleted, the snapshot will become orphaned. You can also set any condition in the code to handle this scenario.)
![image](https://github.com/user-attachments/assets/c9ee1538-4f27-4fb8-b92a-3418f1aae4db)

## By re-running the Lambda function after the instance and volume are removed, the snapshot will be deleted automatically, as it will no longer be attached to any volume.
![image](https://github.com/user-attachments/assets/7c83719b-bc00-4918-9d79-20a8dadb5876)








