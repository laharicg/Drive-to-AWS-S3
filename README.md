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
