# Project-1
Shell script for report the AWS resource usage of EC2, S3, IAM Users, Lambda


#!/bin/bash

#######################################################
# Author : Penchalaiah                                #
# Date :  04th-Oct-2023                               #
#                                                     #
# Version : V1                                        #
#                                                     #
# This script will report the AWS resource usage      #
#######################################################

set -x

# AWS S3
# AWS EC2
# AWS IAM Users
# AWS Lambda

# List S3 Buckets
echo "Print list of S3 buckets"
aws s3 ls

# List EC2 Instances
echo "Print list of EC2 Instances"
aws ec2 describe-instances | jq '.Reservations[].Instances[].InstanceId'

# List IAM Users
echo "Print list of IAM Users"
aws iam list-users | jq '.Users[].UserId'

# List Lambda
echo "Print list of Lambda functions"
aws lambda list-functions

:wq!
