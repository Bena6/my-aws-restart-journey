# my-aws-restart-journey
This project demonstrates how to host a static website using Amazon S3. It includes setting up a custom domain using Route 53, and enabling HTTPS using CloudFront and AWS Certificate Manager.

Core AWS Services Used:

First, I use S3 to:
- Store the website files
- Enable static website hosting
- Allow public read access so anyone can view the website
**Amazon S3** (Simple Storage Service) is an object storage service that offers industry-leading scalability, data availability, security, and performance.

  Steps to create an S3 bucket:
  
  Go to the S3 Console
  Click "Create Bucket"
  Bucket Name: my-website-bucket
  Uncheck "Block all public access"
  Enable Static Website Hosting under "Properties"

I also use Route 53
Route53 is AWS’s Domain Name System (DNS) service.

I use Route 53 to:

- Register a domain name (e.g., mywebsite.com)

- Point that domain to our S3 website

**Amazon Route 53:** Provides DNS routing and domain management; integrates with ACM
for HTTPS/TLS.



