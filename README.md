# Visa-Decision-Prediction-System


- MongoDB :   https://www.mongodb.com/cloud/atlas/register
- MLOPs Tool : https://www.evidentlyai.com/
- FlowChart Tool : https://whimsical.com/
- Data: https://www.kaggle.com/datasets/moro23/easyvisa-dataset

## Git Basic Commands

git add .
git status
git commit -n "WRITE MESSAGE HERE" 
git push origin main

If any warning such as: in the working copy of '____.ipynb', LF will be replaced by CRLF the next time Git touches it
git config --global core.autocrlf true


## Create a Virtual ENV and Activate it

conda create -n visa_env python=3.8 -y
conda activate visa_env

## To setup a Local Package, we use -e . in the requirement file and Install the required packages
pip install -r requirements.txt


## Export the environment variable

export MONGODB_URL="mongodb+srv://<username>:<password>...."

export AWS_ACCESS_KEY_ID=<AWS_ACCESS_KEY_ID>

export AWS_SECRET_ACCESS_KEY=<AWS_SECRET_ACCESS_KEY>

## AWS-CICD-Deployment-with-Github-Actions

1. Login to AWS console.

2. Create IAM user for deployment

3. Create ECR repo to store/save docker image
- Save the URI: 315865595366.dkr.ecr.us-east-1.amazonaws.com/visarepo

4. Create EC2 Instance (Ubuntu)

5. Open EC2 and Install docker in EC2 Machine:

6. Configure EC2 as self-hosted runner:
setting>actions>runner>new self hosted runner> choose os> then run command one by one

7. Setup github secrets such as:
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO

### Details for Step 2 and Step 5

#### Step 2(Create IAM user for deployment): In Details 

1. EC2 access : It is virtual machine

2. ECR: Elastic Container registry to save your docker image in aws


#Description: About the deployment

1. Build docker image of the source code

2. Push your docker image to ECR

3. Launch Your EC2 

4. Pull Your image from ECR in EC2

5. Lauch your docker image in EC2

#Policy:

1. AmazonEC2ContainerRegistryFullAccess

2. AmazonEC2FullAccess



#### Step 5 (Open EC2 and Install docker in EC2 Machine), In Details:

#optinal

sudo apt-get update -y

sudo apt-get upgrade

#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
