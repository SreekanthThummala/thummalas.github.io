# aws-static-website
A simple website for static web hosting in AWS

Building a simple website using Amazon Web Services (AWS) can seem daunting at first, but with the right tools and a bit of guidance, it can be a straightforward process. In this README, we'll walk through the steps of creating a website using AWS CloudFront and S3 Bucket, providing sample code along the way.

## Prerequisites
- AWS account
- AWS CLI

## Steps

### Step 1: Create an S3 Bucket
To create an S3 Bucket, which will be used to store the files for your website, log in to the AWS Management Console, navigate to the S3 service, and select "Create Bucket." Give your bucket a unique name, select the region you want to use, and click "Create."

### Step 2: Upload your website files
Once your S3 Bucket has been created, you can upload the files for your website. To do this, navigate to the S3 Bucket you just created, select "Upload," and choose the files you want to upload. Make sure to set the permissions for your files to public so that they can be accessed by anyone visiting your website.

### Step 3: Create a CloudFront Distribution
The next step is to create a CloudFront Distribution, which will be used to deliver your website's files to users. To do this, navigate to the CloudFront service in the AWS Management Console and select "Create Distribution." Choose the "Web" delivery method and select the S3 Bucket you created in step 1 as the origin.

### Step 4: Update your DNS settings
The final step is to update your domain's DNS settings to point to the CloudFront Distribution you just created. This will allow users to access your website using your domain name. To do this, you'll need to log in to the service where you registered your domain and update the DNS settings to include a CNAME record pointing to the CloudFront Distribution URL.

## Sample Code
Here is a sample code that you can use to create S3 Bucket and CloudFront Distribution using AWS CLI:
```bash
# Create an S3 Bucket
aws s3 mb s3://my-website-bucket

# Upload files to the S3 Bucket
aws s3 cp index.html s3://my-website-bucket/
aws s3 cp style.css s3://my-website-bucket/

# Create a CloudFront Distribution
aws cloudfront create-distribution --origin-domain-name my-website-bucket.s3.amazonaws.com --default-root-object index.html
```

### Additional Resources
A sample index.html file in the repo that you can use to create a basic website. You can customize the content to fit your needs.
A sample style.css file that you can use to add some basic styling to your website.

### Note
Keep in mind that this is just a basic example, and there are many other features and options available to you when building a website using AWS. Make sure to link the style.css file in your index.html file.
