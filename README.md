# Notes

This is a personal project that I use to store my notes in an S3 bucket. 


## Install

```sh
curl -s -o /usr/local/bin/notes https://raw.githubusercontent.com/nav/notes/main/notes && chmod +x /usr/local/bin/notes
```

## Usage

```sh
Usage: [DEBUG=1] notes <command>

This script allows you to copy data to S3. You need a few things in place to use
this tool. You must have aws-cli and jq installed.

Additionally, you need to provide:
 - Name of the AWS profile if it's different from "default"
 - ARN of the role that can be assumed when copying files to S3
 - Name of the S3 Bucket where files will be uploaded
 - Local directory to be used for syncing

Set DEBUG=1 to enable debug messages.

Positional arguments:

init              Create notes configuration.
push              Push and sync data with S3.
pull              Pull data from S3 into empty folder.
liink <object>    Generate presigned link to a private object.
```

To get started, run `notes init` inside an empty directory. It'll create a config 
file and pull the contents of S3 bucket into the current directory.

## TODO

- Share Terraform config to setup
  - S3 Bucket and policies
  - CloudFront distribution
  - Route53 and ACM 
  - IAM Roles and Policies