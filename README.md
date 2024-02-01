# Telegram Bot for detecting objects in a photo

![image](https://github.com/ShirinLabay/aws_project/assets/62480878/e1ce818f-f70a-432c-beb1-32a988f2ade4)

## Technologies Used:
AWS Services: EC2, Docker, ALB, Secret Manager, SQS, S3, DynamoDB, CloudWatch, Lambda, Autoscaling Group, etc.
Programming Languages: Python, Boto3, etc. 

### The project involves the implementation of a microservices architecture on Amazon Web Services (AWS) to deploy and manage two key services: Polybot and Yolo5. Below are the main components and functionalities of each service:
## Polybot Service:
Deployed on a micro EC2 instance as a Docker container.
Ensures high availability across at least two different Availability Zones (AZ).
Utilizes an Application Load Balancer (ALB) to route traffic securely over HTTPS.
Telegram token is securely stored in AWS Secret Manager.

## Yolo5 Service:
Runs on a micro EC2 instance as a Docker container.
Implements auto-scaling using an Autoscaling Group (ASG).
ASG scales in and out based on the number of messages in an SQS queue.
Yolo5 instances consume jobs from the SQS queue and process images from an S3 bucket.
Results are stored in DynamoDB, and a GET request is made to the Polybot service for retrieval.

