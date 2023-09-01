# Using Terraform to stand up a 3 Tier AWS Virtual Private Cloud (VPC).
### create the vpc main.tf file and the varaibles.tf side by side
### Inside the main.tf file, create the following resources:
#### - create the vpc.
#### - create internet gateway and attach it to the vpc
## Inside the variables file
### use data source to get a list of all availability zones in prefered regions.
### create public subnet in az1 (all AZs are indexed [0,1])
### create public subnet in az2
### create route table and add a public route
### associate public subnet az1 to the "public route table"
### associate public subnet az2 to the "public route table"
### create a private application subnet in az1
### create a private application subnet in az2
### create a private database subnet in az1
### create a private database subnet in az2
####  (review the main.tf file code and save)
### On the other hand, create variables as follows;
#### - for the region and project_name.
#### - create variable for the public_subnet_az1_cidr
#### - create variable for the public_subnet_az2_cidr
#### - create variable for the private_app_subnet_az1_cidr
#### - create variable for the private_app_subnet_az2_cidr
#### - create variable for the private_db_subnet_az1_cidr
#### - create variable for the private_db_subnet_az2_cidr
##### (review the variable file code and save)
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
### create a reference for the inter_gateway in the output file.
       (review the out put code and save)
# reference the created vpc module above in another project if necessary.
  *  This will demonstrate the re-usability of terraform modules
        * The ease of application and replication that Iac i terraform gives
#### I created another folder called(appleSCH-website).
#### The appleSCH-website project will store its terraform state file in an s3.
### - configure aws provider for the apple-sch-website project.
####  I opened a backend.tf file in the project folder for the state file
#### - Log into the Amazon console and create an s3 bucket.
#### - Enter the bucket name, key, region and profile in the backend.tf file.
#### - Its possible to enable state locking using a dynamoDB. 
+ This prevents multiple team members from applying changes simultaneously, which could result in an inconsistent or corrupt state.
+ Reduce the risk of state corruption that could occur if multiple write operations happen concurrently.
+ Locking adds an extra layer of protection against unintended modifications, helping ensure that critical resources are not accidentally destroyed or altered.
+ Good for auditing changes and understanding sequence of events incase of troubleshooting.
#### - create vpc for the appleSCH-website project
#### - reference the vpc module already created under the interview project folder
#### - double period takes one up two dirs
#### - list all variables for the vpc
