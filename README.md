# Terraform_EC2-instance-creation

Creating ec2 intsance using terraform.
<br>
When launching a resource in AWS there are 3 things to consider:
1.How will you authenticate to AWS?
<br>
2.Which region will the resource be launched in?
<br>
3.Which resource do you want to launch?
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