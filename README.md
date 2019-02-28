# aws-vpc-destroy
Python boto3 script to delete a VPC

#### Why did I write this?
Deleting a VPC using boto3 is surprisingly difficult. You can't just follow the steps you would in the console as
it performs actions on your behalf. Here are some examples of additional steps you have to handle.

* Delete all subnets
* Delete custom security groups
* Delete Transit Gateway attachments
* Detach IGWs

#### Usage

```
$ ./vpc_destroy.py -h
usage: vpc_destroy.py [-h] --vpc_id VPC_ID [--services SERVICES]
                      [--region REGION]

required arguments:
  --vpc_id VPC_ID      Please include your vpc_id

optional arguments:
  --services SERVICES  comma-separated list of AWS services to tear down
  --region REGION      AWS region
```

The only currently supported AWS service is EC2.

#### Warning
This code is not ready for production. For now, please consider it primary use as an example of how to perform
certain actions using boto3.

#### Acknowledgments
This script would not have been possible without @neilswinton, @vernhart, @alberto-morales, and @Fabian1976. I took their advice
and incorporated their code snippets into this tool.
