# equalexpertsspringpetclinic

This Project is to build a pipeline to deploy the media wiki helm chart to AWS EKS in us-east-1 region.

Prerequisites to run the code

1. Linux Terminal
2. Docker

Steps to follow:

1. docker run -it arsenal14h/eks-utils /bin/bash  # The container will be created from the image in my docker hub repository.Image is made public only for this project.

# Run below inside the container
2. git clone https://github.com/so008mo/equalexperts.git

2. cd /equalexperts

3. aws configure    # Please enter your secret access key and access id as per the AWS account that you want the project to be built.

4. ansible-playbook main.yml

Components that will be deployed

1. VPC, Two private, two public subnets, two NAT gateways, one internet gateway & one virtual private gateway

2. EKS Cluster and one EKS Nodegroup of t2.medium instance type

3. Cluster Autoscaler to handle any capacity requests


Additional comments.

1. The manual steps done above can be done by any CI tool like Jenkins or Gitlab CI.

Note- Post competion of the pipeline please wait for 3-4 mins and then Browse the petclinic URL mentioned in the output of the playbook.
