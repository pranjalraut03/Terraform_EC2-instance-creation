# Terraform_EC2-instance-creation
Creating ec2 intsance using terraform.
provider "aws" {
    region = "us-west-2" 
    
}
resource "aws_instance" "my_ec2" {
    ami = "ami-05b622b5fa0269787"
    instance_type = "t2.micro"
}