# CloudFormation
his CloudFormation template creates a basic AWS infrastructure setup including a Virtual Private Cloud (VPC), subnets, an Application Load Balancer, an S3 bucket, and Amazon Cognito for user authentication. It's designed to be a foundation for building scalable and secure web applications.

Documentation:
1. VPC (Virtual Private Cloud):
Resource Type: AWS::EC2::VPC
Description: Defines a VPC with a specified CIDR block.
Properties:
CidrBlock: Specifies the range of IP addresses for the VPC.
Tags: Provides metadata in the form of key-value pairs for resource identification.
2. Subnets:
Resource Type: AWS::EC2::Subnet
Description: Defines two subnets within the VPC, each in a different availability zone.
Properties:
VpcId: References the VPC in which the subnet will be created.
CidrBlock: Specifies the IP address range for the subnet.
AvailabilityZone: Specifies the availability zone where the subnet will be created.
Tags: Provides metadata for subnet identification.
3. Security Group:
Resource Type: AWS::EC2::SecurityGroup
Description: Defines a security group for the Application Load Balancer.
Properties:
GroupDescription: Provides a description for the security group.
VpcId: References the VPC to which the security group will be attached.
4. Application Load Balancer:
Resource Type: AWS::ElasticLoadBalancingV2::LoadBalancer
Description: Sets up an Application Load Balancer to distribute incoming traffic across multiple targets.
Properties:
Subnets: Specifies the subnets in which the load balancer will be deployed.
SecurityGroups: Specifies the security groups allowed to access the load balancer.
Tags: Provides metadata for load balancer identification.
5. S3 Bucket:
Resource Type: AWS::S3::Bucket
Description: Creates an S3 bucket for storing data.
Properties:
BucketName: Specifies the name of the S3 bucket.
AccessControl: Sets the access control for the bucket (in this case, private).
Tags: Provides metadata for bucket identification.
6. Amazon Cognito:
UserPool:
Resource Type: AWS::Cognito::UserPool
Description: Creates a user pool for managing user authentication.
Properties:
UserPoolName: Specifies the name of the user pool.
Policies: Defines password policies for user authentication.
Schema: Specifies user attributes such as email and password.
UserPoolClient:
Resource Type: AWS::Cognito::UserPoolClient
Description: Creates a client application for accessing the user pool.
Properties:
ClientName: Specifies the name of the user pool client.
UserPoolId: References the user pool to which the client belongs.
This CloudFormation template provides a foundational infrastructure setup for building web applications with scalable and secure features, including user authentication through Amazon Cognito.
