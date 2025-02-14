# Automating creation of IAM Resources LAB

This project contains a CloudFormation template that automates the creation of IAM resources, including users, groups, and a Lambda function for logging user credentials.

The template creates the following resources:

* Two IAM users: `s3-user` and `ec2-user`
* Two IAM groups: `S3ReadOnlyGroup` and `EC2ReadOnlyGroup`
* Two IAM policies: `S3ReadOnlyPolicy` and `EC2ReadOnlyPolicy`
* A Lambda function: `LogNewUserCredentials`
* An EventBridge rule: `IAMUserCreationRule`
* Two SSM parameters: `UserEmail-s3` and `UserEmail-ec2`

The template also grants the necessary permissions to the Lambda function to write to CloudWatch logs and read from SSM parameters.

## Getting Started

To deploy this project, follow these steps:

1. Clone the repository to your local machine.
2. Create an S3 bucket to store the Lambda function code.
3. Upload the `lambda_function.py` file to the S3 bucket.
4. Create a CloudFormation stack using the `template.yaml` file.
5. Pass the name of the S3 bucket as a parameter to the CloudFormation stack.

## Security

This project uses the following security best practices:

* IAM users and roles are created with the principle of least privilege.
* IAM policies are attached to groups rather than users.
* The Lambda function is configured to use an IAM role.
* The Lambda function is configured to write to CloudWatch logs.
* The SSM parameters are encrypted using KMS.

## Contributing

Contributions are welcome! Please open a pull request to contribute to this project.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
