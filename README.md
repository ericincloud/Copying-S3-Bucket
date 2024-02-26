# Copying-S3-Bucket
#### How to copy and delete files in Amazon S3! <br><br> This guide will demonstrate how to copy files, syncing two S3 Buckets, and empyting + deleting an S3 Bucket!
## Step 1:
#### First, have two S3 buckets set up. In this example, there is a source bucket and a destiantion bucket. The source bucket contains 3 files - index.html, style.css, and avatarmaker.png. The destination bucket will be empty.

#### From the AWS Console, launch the AWS CloudShell. To copy the "style.css" file to the desination bucket, we must use this command: "aws s3 cp s3://testbucket-source1231/style.css s3://testbucket-destination1231/style.css"

