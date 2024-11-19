 # SETTING UP A SCALABLE FILE STORAGE SYSTEM USING AMAZON ELASTIC FILE SYSTEM
  ## AIM
       To  setting up a scalable file storage system using Amazon Elastic File System (EFS) for two EC2 instances in different availability zones. 
## PROBLEM STATEMENT
This experiment demonstrates how to configure Amazon EFS to provide a shared storage solution for two Linux EC2 instances across different availability zones, enabling easy data sharing. The aim is to ensure both instances can mount and access the EFS file system and validate data consistency across instances.

## ALGORITHM
 ### Steps 1: Create two EC2 instances in different availability zones.
 ### Steps 2: Set up a security group that allows necessary communication between the instances and EFS.
 ### Steps 3: Create an EFS file system and mount it to both EC2 instances.
 ### Steps 4: Ensure that the EC2 instances can access the file system and share data between them.

## COMMANDS:
### EC2 Instance 1

```
sudo su
yum install httpd -y
yum install -y amazon-efs-utils
mount -t efs -o tls fs-064645ac116a12816:/ /var/www/html
cd /var/www/html
vi file  # Create a file and add some text
```

### EC2 Instance 2

```
sudo su
yum install httpd -y
yum install -y amazon-efs-utils
mount -t efs -o tls fs-064645ac116a12816:/ /var/www/html
cd /var/www/html
ls
cat file  # Verify shared access by reading content created in Instance 1
```

## OUTPUT
### REG NUMBER: 212223220021
### NAME: DINESHKARTHIK N
![creation file system 1](https://github.com/user-attachments/assets/5e1ff2df-f160-43a6-acc7-e473f01be866)
![creation file system 2](https://github.com/user-attachments/assets/22eb5978-74c1-4575-a672-262f4da48eda)
![file creation on machine (1)](https://github.com/user-attachments/assets/38606cee-bc70-418b-8171-dcd9d3fde5f4)
![file creation on machine (2)](https://github.com/user-attachments/assets/1d0161cb-116c-4bba-b7da-bb652041e2af)

## RESULT
Successfully set up a scalable file storage system using Amazon EFS shared between two Linux EC2 instances in different availability zones, enabling consistent data sharing.
