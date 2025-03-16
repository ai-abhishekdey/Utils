## Amazon Web Services (AWS)-CLI commands

* **Author: Abhishek Dey**

* **Date: March 16, 2025**

## Install aws-cli

```
sudo apt-get install awscli

```

## Configure aws-cli

* **aws configure**

```
abhishek@abhishek:~$ aws configure
AWS Access Key ID [****************XCW7]: A******************F
AWS Secret Access Key [****************ooxt]: B**********/***/***P
Default region name [None]: us-east-1
Default output format [None]: json

```
* **cat ~/.aws/config**

```
abhishek@abhishek:~$ cat ~/.aws/config 
[default]
region = us-east-1
output = json

```
* **cat ~/.aws/credentials**

```
abhishek@abhishek:~$ cat ~/.aws/credentials 
[default]
aws_access_key_id = A******************F
aws_secret_access_key = B**********/***/***P


```

* **aws ec2 describe-instance-status**

```
abhishek@abhishek:~$  aws ec2 describe-instance-status
{
    "InstanceStatuses": [
        {
            "AvailabilityZone": "us-east-1a",
            "InstanceId": "i-***********",
            "InstanceState": {
                "Code": 16,
                "Name": "running"
            },
            "InstanceStatus": {
                "Details": [
                    {
                        "Name": "reachability",
                        "Status": "passed"
                    }
                ],
                "Status": "ok"
            },
            "SystemStatus": {
                "Details": [
                    {
                        "Name": "reachability",
                        "Status": "passed"
                    }
                ],
                "Status": "ok"
            }
        }
    ]
}

```

## SSH connect from local machine to EC2 instance

```

ssh -i "aws-key-pair.pem" ubuntu@ec2-xx-xxx-xxx-xx.compute-1.amazonaws.com

```


## Copy file from local machine to EC2 instance

```

scp -i "aws-key-pair.pem" test_img.jpg  ubuntu@ec2-xx-xxx-xxx-xx.compute-1.amazonaws.com:/home/ubuntu/ad-workspace

```

## Copy folder from local machine to EC2 instance

```
scp -i "aws-key-pair.pem" -r aws_upload  ubuntu@ec2-xx-xxx-xxx-xx.compute-1.amazonaws.com:/home/ubuntu/ad-workspace

```

## Copy file from EC2 instance to local machine

```

scp -i "aws-key-pair.pem"  ubuntu@ec2-xx-xxx-xxx-xx.compute-1.amazonaws.com:/home/ubuntu/ad-workspace/test_img.jpg ./data_from_ec2/

```

## Copy folder from EC2 instance to local machine

```

scp -i "aws-key-pair.pem" -r  ubuntu@ec2-xx-xxx-xxx-xx.compute-1.amazonaws.com:/home/ubuntu/ad-workspace/aws_upload ./data_from_ec2/

```

## List of all buckets in aws-s3

```

aws s3 ls

```

## List of folders inside aws-s3 bucket

```
aws s3 ls s3://<bucket>/

```

## List of files and folders inside aws-s3 bucket

```
aws s3 ls s3://<bucket>/ --recursive

```
## Copy single file to a aws-s3 bucket

```
aws s3 cp test_img.jpg s3://abhishek-workspace

```

## Copy folder along with files to a aws-s3 bucket

```
aws s3 cp aws_upload/ s3://abhishek-workspace/aws_upload --recursive

aws s3 cp aws_upload2/ s3://abhishek-workspace/aws_upload2 --recursive


```

## Delete a file inside a aws-s3 bucket

```
aws s3 rm s3://abhishek-workspace/test_img.jpg

```

## Delete all .jpg files inside a folder in aws-s3 bucket

```
aws s3 rm s3://abhishek-workspace/aws_upload2/ --recursive --exclude "*" --include "*.jpg"

```

## Delete a folder inside a aws-s3 bucket

```
aws s3 rm s3://abhishek-workspace/aws_upload2/

```

## Check the memory usage of aws-s3 bucket

```
aws s3 ls --summarize --human-readable --recursive s3://abhishek-workspace

```

```
2025-03-14 16:07:37  148.0 KiB aws_upload/000000002753.jpg
2025-03-14 16:07:37   97.9 KiB aws_upload/000000003745.jpg

Total Objects: 2
   Total Size: 245.9 KiB

```

## References:

* https://www.youtube.com/watch?v=0SYV7o_fd50

* https://www.youtube.com/watch?v=4Qd2pThNTtY

* https://www.youtube.com/watch?v=wmcKUcgVbH8

* https://www.youtube.com/watch?v=2m4_AdKbSY4

* https://www.youtube.com/watch?v=57TCFZG08oM

* https://www.youtube.com/watch?v=8UqtMcX_kg0
