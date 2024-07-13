### Hands-On Task for AWS CLI

**Objective:**
Students will use the AWS CLI to perform basic operations with Amazon S3, EC2, and IAM services. This hands-on task will help them apply what they've learned and test their understanding of the AWS CLI.

### Task Overview:
1. Configure AWS CLI
2. Create and manage S3 buckets and objects
3. Launch and manage an EC2 instance
4. Create and manage IAM users

### Detailed Instructions:

#### Part 1: Configure AWS CLI
1. **Install AWS CLI:** Ensure AWS CLI is installed on your machine. Use the following command to check the installation:
   ```sh
   aws --version
   ```
2. **Configure AWS CLI:** Configure your AWS CLI with the provided credentials.
   ```sh
   aws configure
   ```
   Enter the following details:
   - AWS Access Key ID
   - AWS Secret Access Key
   - Default region name (e.g., `us-west-2`)
   - Default output format (e.g., `json`)

#### Part 2: S3 Operations
1. **Create an S3 Bucket:**
   ```sh
   aws s3 mb s3://my-unique-bucket-name
   ```
2. **List All S3 Buckets:**
   ```sh
   aws s3 ls
   ```
3. **Upload a File to the S3 Bucket:**
   Create a text file named `testfile.txt` on your local machine. Then, upload it to your S3 bucket.
   ```sh
   aws s3 cp testfile.txt s3://my-unique-bucket-name/
   ```
4. **List Objects in the S3 Bucket:**
   ```sh
   aws s3 ls s3://my-unique-bucket-name/
   ```
5. **Download the File from the S3 Bucket:**
   ```sh
   aws s3 cp s3://my-unique-bucket-name/testfile.txt downloaded_testfile.txt
   ```
6. **Delete the File from the S3 Bucket:**
   ```sh
   aws s3 rm s3://my-unique-bucket-name/testfile.txt
   ```
7. **Delete the S3 Bucket:**
   ```sh
   aws s3 rb s3://my-unique-bucket-name --force
   ```

#### Part 3: EC2 Operations
1. **Launch an EC2 Instance:**
   Launch a new EC2 instance using the Amazon Linux 2 AMI. Use the following command, replacing `YOUR_KEY_PAIR_NAME` with your actual key pair name.
   ```sh
   aws ec2 run-instances --image-id ami-0abcdef1234567890 --count 1 --instance-type t2.micro --key-name YOUR_KEY_PAIR_NAME
   ```
2. **List EC2 Instances:**
   ```sh
   aws ec2 describe-instances
   ```
3. **Stop the EC2 Instance:**
   Identify the instance ID from the previous command’s output and stop the instance.
   ```sh
   aws ec2 stop-instances --instance-ids i-1234567890abcdef0
   ```
4. **Start the EC2 Instance:**
   ```sh
   aws ec2 start-instances --instance-ids i-1234567890abcdef0
   ```
5. **Terminate the EC2 Instance:**
   ```sh
   aws ec2 terminate-instances --instance-ids i-1234567890abcdef0
   ```

#### Part 4: IAM Operations
1. **Create an IAM User:**
   ```sh
   aws iam create-user --user-name test-user
   ```
2. **List IAM Users:**
   ```sh
   aws iam list-users
   ```
3. **Attach Policy to IAM User:**
   Attach the `AmazonS3ReadOnlyAccess` policy to the user `test-user`.
   ```sh
   aws iam attach-user-policy --user-name test-user --policy-arn arn:aws:iam::aws:policy/AmazonS3ReadOnlyAccess
   ```
4. **Delete the IAM User:**
   Detach the policy first, then delete the user.
   ```sh
   aws iam detach-user-policy --user-name test-user --policy-arn arn:aws:iam::aws:policy/AmazonS3ReadOnlyAccess
   aws iam delete-user --user-name test-user
   ```

### Submission:
Students should submit a SINGLE PDF document containing the following:
1. The output of each command executed during the hands-on task.
2. Screenshots of the AWS Management Console showing the S3 bucket, EC2 instance, and IAM user at various stages.

### Evaluation Criteria:
- Correct execution of AWS CLI commands.
- Proper configuration and usage of AWS CLI.
- Successful completion of each part of the task.
- Clear documentation and submission of outputs and screenshots.

By completing this hands-on task, students will demonstrate their ability to use the AWS CLI for basic cloud operations, enhancing their practical understanding of AWS services.
