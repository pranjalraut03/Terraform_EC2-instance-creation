# Terraform_EC2-instance-creation
Creating ec2 intsance using terraform.
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