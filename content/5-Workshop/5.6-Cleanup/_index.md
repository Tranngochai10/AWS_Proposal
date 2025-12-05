---
title : "Testing and Cleanup"
date : 2025-09-09
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

## Testing and Cleanup

### Testing Your API

Before cleaning up, make sure to test all endpoints:

1. **Create Task** - POST request to `/tasks`
2. **List Tasks** - GET request to `/tasks`
3. **Get Task** - GET request to `/tasks/{id}`
4. **Update Task** - PUT request to `/tasks/{id}`
5. **Delete Task** - DELETE request to `/tasks/{id}`

### Cleanup Steps

To avoid incurring charges, delete all resources created during this workshop.

#### Step 1: Delete API Gateway

1. Go to **API Gateway** console
2. Select your API: `TaskManagementAPI`
3. Click **Actions** → **Delete API**
4. Type the API name to confirm
5. Click **Delete**

#### Step 2: Delete Lambda Functions

1. Go to **Lambda** console
2. Delete each function:
   - `createTask`
   - `listTasks`
   - `getTask`
   - `updateTask`
   - `deleteTask`

For each function:
- Select the function
- Click **Delete**
- Type "delete" to confirm
- Click **Delete**

#### Step 3: Delete DynamoDB Table

1. Go to **DynamoDB** console
2. Select table: `tasks`
3. Click **Delete**
4. Type "delete" to confirm
5. Click **Delete**

#### Step 4: Delete IAM Role

1. Go to **IAM** console
2. Click **Roles**
3. Find role: `lambda-dynamodb-role`
4. Click on the role
5. Click **Delete**
6. Type the role name to confirm
7. Click **Delete**

#### Step 5: Delete CloudWatch Log Groups (Optional)

1. Go to **CloudWatch** console
2. Click **Log groups**
3. Delete log groups for each Lambda function:
   - `/aws/lambda/createTask`
   - `/aws/lambda/listTasks`
   - `/aws/lambda/getTask`
   - `/aws/lambda/updateTask`
   - `/aws/lambda/deleteTask`

### Verification

After cleanup, verify that:
- ✅ No API Gateway APIs exist
- ✅ No Lambda functions exist
- ✅ No DynamoDB tables exist
- ✅ IAM role is deleted

### Summary

Congratulations! You have successfully:

1. ✅ Created a DynamoDB table for data storage
2. ✅ Created Lambda functions for business logic
3. ✅ Configured API Gateway REST API
4. ✅ Integrated Lambda with API Gateway
5. ✅ Built a complete serverless REST API

### What You Learned

- How to create and configure DynamoDB tables
- How to write Lambda functions in Python
- How to create REST APIs with API Gateway
- How to integrate Lambda with API Gateway
- How to handle HTTP requests and responses
- Serverless architecture patterns

### Next Steps

- Add authentication using AWS Cognito
- Add API rate limiting
- Implement input validation
- Add error handling and logging
- Deploy to production stage
- Set up monitoring and alerts

Thank you for completing this workshop!
