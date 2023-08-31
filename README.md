# Using Terraform to stand up a 3 Tier AWS Virtual Private Cloud (VPC).
## create the vpc main.tf file and the varaibles.tf side by side
### Inside the main.tf file, create the following resources:
#### - create the vpc.
#### - create internet gateway and attach it to the vpc
### Inside the variables file
##### (use data source to get a list of all availability zones in prefered regions).
### --> create public subnet in az1 (all AZs are indexed [0,1])
### --> create public subnet in az2
### --> create route table and add a public route
### associate public subnet az1 to the "public route table"
### associate public subnet az2 to the "public route table"
### . create a private application subnet in az1
### . create a private application subnet in az2
### . create a private database subnet in az1
### . create a private database subnet in az2
## On the other hand, create variables as follows;
#### - for the region and project_name.
#### - create variable for the public_subnet_az1_cidr
#### - create variable for the public_subnet_az2_cidr
#### - create variable for the private_app_subnet_az1_cidr
#### - create variable for the private_app_subnet_az2_cidr
#### - create variable for the private_db_subnet_az1_cidr
#### - create variable for the private_db_subnet_az2_cidr
## Develop the output.tf file 
### (this allows us to export some values from this vpc, and we can reference them when we create other resources)
### The first output will export our region.
#### - export the project name
#### - export the vpc id as referenced in the main.tf file
#### - export the id of the public_subnet_az1
#### - export the id of the public_subnet_az2
#### - export the id of the private_app_subnet_az1
#### - export the id of the private_app_subnet_az2
#### - export the id of the private_db_subnet_az1
#### - export the id of the private_db_subnet_az2
