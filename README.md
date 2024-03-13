**Requirements**
You must have Terraform installed on your computer.
You must have an AWS (Amazon Web Services) account.
It uses the Terraform AWS Provider that interacts with the many resources supported by AWS through its APIs.
This code was written for Terraform 0.10.x.
Using the code
Configure your AWS access keys.

Important: For security, it is strongly recommend that you use IAM users instead of the root account for AWS access.

Setting your credentials for use by Terraform can be done in a number of ways, but here are the recommended approaches:

The default credentials file

Set credentials in the AWS credentials profile file on your local system, located at:

~/.aws/credentials on Linux, macOS, or Unix

C:\Users\USERNAME\.aws\credentials on Windows

This file should contain lines in the following format:

[default]
aws_access_key_id = <your_access_key_id>
aws_secret_access_key = <your_secret_access_key>
Substitute your own AWS credentials values for the values <your_access_key_id> and <your_secret_access_key>.

Environment variables AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY

Set the AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY environment variables.

To set these variables on Linux, macOS, or Unix, use export:

export AWS_ACCESS_KEY_ID=<your_access_key_id>
export AWS_SECRET_ACCESS_KEY=<your_secret_access_key>
To set these variables on Windows, use set:

set AWS_ACCESS_KEY_ID=<your_access_key_id>
set AWS_SECRET_ACCESS_KEY=<your_secret_access_key>
Initialize working directory.

The first command that should be run after writing a new Terraform configuration is the terraform init command in order to initialize a working directory containing Terraform configuration files. It is safe to run this command multiple times.

terraform init
Validate the changes.

Run command:

terraform plan
Deploy the changes.

Run command:

terraform apply
Test the deploy.

When the terraform apply command completes, use the AWS console, you should see the new EC2 instance created.

Clean up the resources created.

When you have finished, run command:

terraform destroy
