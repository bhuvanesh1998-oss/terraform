

# For s3 Bucket
# Configure the AWS Provider
provider "aws" {
  region  = "ap-south-1"
  profile = "terraform"
}
# Configure the AWS Resource
resource "aws_s3_bucket" "example" {
  bucket = "bhuvi-demo-tf-test-bucket"

  tags = {
    Name        = "My bucket"
    Environment = "Dev"
  }
}
######################################################################################################

#Hard coded credentials in provider block:

provider "aws" {
  region     = "us-west-2"
  access_key = "my-access-key"
  secret_key = "my-secret-key"
}


#Hard-coded credentials are not recommended in any Terraform configuration and risks secret leakage should this file ever be committed to a public version #control system.


#Other settings related to authorization can be configured, such as:
    #• profile
    #• shared_config_files
    #• shared_credentials_files

cd /home/<user-name>/.aws/credentials

#add the below lines:

[terraform]
aws_access_key_id = <access>
aws_secret_access_key = <secret>

#Create profile in providers block:

provider "aws" {
   region     = "ap-south-1"
  profile     = "terraform"
}
