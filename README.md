# Copying-S3-Bucket
#### How to copy and delete files/buckets in Amazon S3! <br> This guide will demonstrate how to copy files, syncing two S3 Buckets, and empyting + deleting an S3 Bucket!
## Step 1: Copying a file to another S3 Bucket
#### First, have two S3 buckets set up. In this example, there is a source bucket and a destiantion bucket. The source bucket contains 3 files - `index.html`, `style.css`, and `avatarmaker.png`. The destination bucket will be empty.

![IMAGE](https://github.com/ericincloud/Copying-S3-Bucket/blob/main/buckets.JPG)
![IMAGE](https://github.com/ericincloud/Copying-S3-Bucket/blob/main/sourcebucket.JPG)

#### From the AWS Console, launch the AWS CloudShell. To copy the `style.css` file to the desination bucket, we must use this command: `aws s3 cp s3://testbucket-source1231/style.css s3://testbucket-destination1231/style.css` 

![IMAGE](https://github.com/ericincloud/Copying-S3-Bucket/blob/main/cloudshell1.JPG)

`style.css` can now be found in the destination bucket! 

![IMAGE](https://github.com/ericincloud/Copying-S3-Bucket/blob/main/destinationbucket1.JPG)

## Step 2: Syncing/Copying all files to another S3 Bucket
#### Now lets copy the rest of the files to the destination bucket! To do this, use this command: `aws s3 sync s3://testbucket-source1231 s3://testbucket-destination1231`

If done correctly, `index.html` and `avatarmaker.png` both will get copied to the destination bucket.

![IMAGE](https://github.com/ericincloud/Copying-S3-Bucket/blob/main/destinationbucket2.JPG)

## Step 3: Emptying an S3 Bucket
#### After syncing/copying the files to the destiantion bucket, the source bucket bucket can now be emptied and deleted. To do so, enter this command: `aws s3 rm s3://testbucket-source1231 --recursive`

If done correctly, the source bucket should be completely emptied!

![IMAGE](https://github.com/ericincloud/Copying-S3-Bucket/blob/main/sourcebucket2.JPG)

## Step 4: Deleting an S3 Bucket
#### Now, lets delete the emptied source bucket. Enter command: `aws s3 rb s3://testbucket-source1231`
Congratulations! All files within the source bucket and the bucket itself should be now deleted! Previous files from the source bucket should be in the destination bucket!

![IMAGE](https://github.com/ericincloud/Copying-S3-Bucket/blob/main/destinationbucket3.JPG)

## Reference

Copy file to another bucket:
`aws s3 cp s3://source-bucket/example.txt s3://destination-bucket/example.txt`

Sync/Copy Entire bucket:
`aws s3 sync s3://source-bucket s3://destination-bucket`

Empty bucket:
`aws s3 rm s3://bucket-name --recursive`

Delete bucket:
`aws s3 rb s3://bucket-name`


