# mlflow-aws-demo


# MLflow on AWS

## MLflow on AWS Setup:

1. Login to AWS console.
2. Create IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo python3 -m pip install venv

sudo python3 -m venv  mlflow_env

source mlflow_env/bin/activate

pip install mlflow

pip install setuptools

pip install awscli

pip install boto3

## Then set aws credentials
aws configure


#Finally 
mlflow server -h 0.0.0.0 --port 5000 --default-artifact-root s3://bucket_name

#open Public IPv4 DNS to the port 5000


#set uri in your local terminal and in your code 
export MLFLOW_TRACKING_URI=http://ec2-23-22-160-239.compute-1.amazonaws.com:5000/
```
