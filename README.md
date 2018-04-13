# Lambda_Auto_Deploy
This function can be used to auto-deploy single or multiple lambda functions based on bucket name as well as the zip file name.
Steps to follow:

1. Create S3 buckets on which you will be pushing your own lambda codes to.

2. Create a lambda function with this code and allow S3 buckets read only access on the buckets we had created in last step and cloudwatch:logs full access. Replace bucketname, key name and lambda function name (your lambda function name on which you need to deploy your zipped code.)

3. Set tiggers on S3 buckets for PUT operations to the lambda funtion created in step 2.

4. Push your zipped code to s3 buckets created in step 1, via CI/CD tools like jenkins. travisCI etc.

5. Your zipped code will be automatically get deployed on the lambda function name you mention in this lamdba function code.

6. You can use this to publish multiple lambda functions just copy-paste the "if" block, replace "if" with "else if" and then put in another "bucket name", "key name" and "lambda function name".

7. You can use same bucket for multiple zips of lambda code and deploy them to multiple lambda functions.
