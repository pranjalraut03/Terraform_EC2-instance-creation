# Terraform_EC2-instance-creation
<br>
Creating ec2 intsance using terraform.
<br>
When launching a resource in AWS there are 3 things to consider:
<br>
<br>
1.How will you authenticate to AWS?
<br>
2.Which region will the resource be launched in?
<br>
3.Which resource do you want to launch?
<br>
First create a .tf file in this case I will use first_ec2.tf
<br>
<br>
Example code for a simple EC2 instance:
<br>
<br>
provider "aws" {
    <br>
    region = "us-west-2" 
    <br>
    
}
<br>
resource "aws_instance" "my_ec2" {
    <br>
    ami = "ami-05b622b5fa0269787"
    <br>
    instance_type = "t2.micro"
    <br>
}
<br>
<br>
Statement 1 (defines what platform, where to launch and method of authentication):
<br>
  1. provider  - In this case it is "aws", the provider has to be specified and it is simply the platform that terraform will be provisioning infrastructure on.
<br>
<br> 
  2. region - This is the AWS Region we want to launch our EC2 instance into. In this case we have chosen "us-west-2"
<br>
<br>
  3. access_key -  This is the 'access key' from the key pair we created for our AWS IAM User, it is part of what allows Terraform to authenticate to AWS.
<br>
<br>
  4.secret_key - This is the 'secret key' from the key pair we created for our AWS IAM User.
<br>
<br>
Statement 2 (defines resource specfications):
<br>
    1.resource - In this case we have specified "aws_instance" the terraform name for an AWS EC2 Instance and secondly "my_ec2" which is what we want to name the instance. Two resource blocks cannot have the same name "my_ec2" will be a unique name in the file. 
<br>
    2.ami - Specifies the Amazon Machine Image, ie. what image (OS specifics) we want to load on the EC2 Instance.
<br>
    3.instance_type - In this case we have specified "t2.micro" this specifies what type of Amazon EC2 we want our instance to be. (How much memory, storage etc.)
<br>
<br>
Every AWS resource has mandatory elements and optional elements to include in a Terraform resource statement. For EC2 you need to specify the resource, ami and instance type. 
<br>
However there are far more elements that optionally can be specified. They are not included here as this is as simple as it gets for launching an EC2. 
<br>