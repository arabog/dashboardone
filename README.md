# Dashboardone
This ia static react app deployed using *AWS S3 bucket* and *Cloudfront*, 
a Content Delivery Network, which cache the site content for low latency for users through the nearest Edge Locations to the users.

https://dashboardone-ten.vercel.app/

https://d21nkuqzcxkysp.cloudfront.net/index.html

![Dashboardone](/https://github.com/arabog/dashboardone/blob/master/S3-CloudFront.png?raw=true "Dashboard")

# Steps
## S3 & Cloud Front
NB: CloudFront, after caching, speeds up the delivery of content to your website

## Step 1. Create S3 Bucket
Leave d bucket policy as it is
Enable Static website hosting under ppties tab and enter index.html

## Step 2. Upload Object to Bucket
Note that the Bucket has not allowed public access, therefore, the Sample.html 
file cannot be accessed via its object URL, such as 
`https://arabog-cloud.s3.amazonaws.com/sample.html`

NB: use d `npm run build` folder content in case of a react app  

## Step 3. Create CloudFront Distribution
S3 bucket accessInfo
Use a CloudFront origin access identity (OAI) to access the S3 bucket.
Origin Access Identity user represents the CloudFront service. The policy 
is a JSON file that defines the access permissions to the bucket object.

Origin domain: `select d s3 bucket u created`.
Origin path: `leave blank`
S3 bucket access: `Yes use OAI (bucket can restrict access to only CloudFront)`
Create new OAI(origin access identity)
Bucket policy: `Yes, update the bucket policy`
Viewer protocol policy: `Redirect HTTP to HTTPS`
Leave other as default



