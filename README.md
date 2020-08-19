# Drag-and-Drop-Image-Uploader-With-AWS-S3

## Intro

**Using**

- Nodejs + Express for backend
- react for front end
- AWS S3 for File Storage

## config

Create a `.env` in the outmost directory, follow the following pattern :

```
accessKeyId=
secretAccessKey=
region=
Bucket=
```

`accessKeyId` and `secretAccessKey` can be created in AWS console, from my secret credentials, Access keys.

`region` can be found in S3's bucket list,

in this example, `region` is `us-east-2`, and `Bucket` is `laharic`.

## Run

1. clone the repository: https://github.com/laharicg/Drive-to-AWS-S3.git
2. one terminal --> cd Drive-to-AWS-S3
   --> npm install
   --> npm start
3. another terminal --> cd client
   --> npm install
   --> npm start

# Steps to access AWS-S3 bucket

## AWS console - free tier -12 motnhs

Create an acccount - asks for credit/ debit card details(just to identify as human and not robot )
IAM - dashboard - Users- Add user - Username - access type-> programmatic access
create group - group name - filter policies -> s3
-> check Amazon S3 full access
-> next -> next
-> create user
upon success,
you get Access key ID & Security Access Key
copy and store both
Now back to IAM, -> Access management -> Users
->select username ->security credentials
->console password : ENABLED
->Create access key
-> copy both `access key` & `secret key` & paste in .env

---

# S3

Click on services -> S3
create bucket - bucket name (to be used in .env)
click on bucket -> permissions ->bucket policy
-> policy generator ->type of policy -s3 bucket policy
->principle \*
->actions : select get object , put object
->ARN (find near pbucket policy editor: ARN: arn:aws:s3:::laharic)
->add statement -> generate policy

copy this generated policy and paste in bucket policy editor(prev. tab)
{
"Version": "2012-10-17",
"Id": "Policy1597738678230",
"Statement": [
{
"Sid": "Stmt1597738674713",
"Effect": "Allow",
"Principal": "_",
"Action": [
"s3:GetObject",
"s3:PutObject"
],
"Resource": "arn:aws:s3:::laharic/_"
}
]
}

check for /_ in this line if not add it-> "Resource": "arn:aws:s3:::laharic/_"

SAVE

---

# region

find in url / bucket info
here its - > us-east-2
