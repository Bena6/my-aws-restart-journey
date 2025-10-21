Project Overview

This project demonstrates how to migrate a small restaurant’s operations to the AWS Cloud by building a static website hosted on Amazon S3 with Cognito authentication and a DynamoDB backend.

The goal is to streamline customer bookings and order management, replacing the restaurant’s manual process with a simple, secure, and scalable cloud-based solution.

Objectives

- Build and deploy a static restaurant website hosted on Amazon S3.  
- Implement user authentication using AWS Cognito.  
- Store customer bookings and orders in Amazon DynamoDB.  
- Optionally, use AWS Lambda and SNS for backend automation and notifications.  
- Prepare a presentation outlining the benefits of AWS migration.


AWS Services Used


Amazon S3 - hosts the static website and images (menu, restaurant photos).
AWS CloudFront - distributes websites globally with caching and faster access.
Amazon Cognito - provides secure user sign-up and sign-in. 
Amazon DynamoDB - stores booking and order data. 
AWS Lambda - processes form submissions and writes data to DynamoDB. 
Amazon API Gateway - connects the website frontend to backend Lambda functions.
Amazon SNS - sends notifications to the restaurant when new orders/bookings are made. 
Step-by-Step Build Guide

Step 1: create a static Website 

1. Create HTML/CSS pages for Home, Menu, Booking, Order, and Sign-In.  
2. Add a booking form (`booking.html`) and an order form (`order.html`).  
3. Store media (images, logo, menu photos) in `/assets/images`.  

Step 2.1: deploy to Amazon S3
Go to AWS Management Console → search S3 → Create Bucket
name: tasty-bistro-website.  
 	Enable Static Website Hosting and Public Access.  
Upload all website files to the bucket.  
Note the website endpoint (e.g., `http://tasty-bistro-website.s3-website-us-east-1.amazonaws.com`).

Enhancements: 

Step 2.2: add Amazon Cloudfront
Use CloudFront for a CDN to improve website performance globally.
Connect your S3 bucket as the origin.


Step 3.1: add Authentication with AWS Cognito
Go to Amazon cognito → Create a User Pool
Enable email or username as the login option.
Allow self-registration so customers can sign up.
After creation, note your Pool ID and App Client ID.
Integrate Cognito into your website using the AWS SDK.  
Restrict access to booking/order pages to authenticated users only.

Step 4: Set Up DynamoDB for Bookings and Orders
Go to DynamoDB → Create Table
- Table 1: Bookings → Partition Key: `BookingID`
- Table 2: Orders → Partition Key: `OrderID`

Step 5: Create Lambda Functions
Create functions to insert booking and order data into DynamoDB:
Each Lambda function connects via API Gateway:
createBooking → Inserts booking data into DynamoDB.
createOrder → Inserts order data into DynamoDB.
getUserBookings → Retrieves bookings for a specific user


Step 6: AWS SNS (Simple Notification Service)
We use AWS SNS to notify staff when a new booking/order is received. We will use AWS Lambda to trigger the SNS topic after a successful database write.

