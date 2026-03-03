# Task 3: IAM, RBAC, and Least Privilege (AWS & Azure)

## Objective
To implement Role-Based Access Control (RBAC) and the Principle of Least Privilege across AWS and Azure environments.

## AWS Implementation (IAM)
1. **User Creation**: Created a `Developer` user in AWS IAM.
2. **Standard Access**: Attached the `AmazonEC2FullAccess` policy to allow VM management.
3. **Least Privilege**: Created and attached a custom JSON policy (`DenyS3DeletePolicy`) to explicitly deny S3 bucket and object deletion.
4. **Verification**: Confirmed that the user can manage EC2 instances but receives an "Access Denied" error when attempting to delete S3 resources.

## Azure Implementation (Entra ID & RBAC)
1. **User Creation**: Created an `intern-developer` user in Microsoft Entra ID.
2. **Scope-Based Access**: 
   - Assigned the **Reader** role at the Resource Group level (`HA-Task2-RG`).
   - Assigned the **Contributor** role only to a specific resource (`VM-Set-1`).
3. **Verification**: 
   - **Success**: The user successfully restarted `VM-Set-1`.
   - **Failure**: The user received an "Authorization failed" error when attempting to restart `VM-Set-2`, proving the restriction to a single resource.

## Proofs
* **AWS_EC2_Success.png** & **AWS_S3_Denied.png**
* **Azure_User_Created.png**, **Azure_VM1_Contributor.png**, & **Azure_VM2_Denied.png**, **Azure_VM1_Restarted.png**