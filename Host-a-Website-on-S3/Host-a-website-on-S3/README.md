## Introduction
Let’s host our very own website on Amazon S3!
We will use S3 (Simple Storage Service) to create a public-facing static website by uploading files and configuring permissions.

### Cost
(Eligible under AWS Free Tier)

#### Objectives:

Create an Amazon S3 Bucket.

Upload HTML and image files.

Configure static website hosting.

Make objects publicly accessible.

Delete all resources at the end.

##### Key Concepts

Amazon S3

A storage service that allows you to store and retrieve data over the internet.

Hosting a Website

Hosting means making your content publicly accessible online.

ACL (Access Control List)

Defines permissions for who can access specific objects within S3.

Static Website Hosting

Amazon S3 can host websites composed of HTML and image files.

### Step 1: Create an S3 Bucket

Log in to your AWS console

Search for S3

Click Create bucket

Bucket name: XYZ-website-project-NAME

Select your nearest AWS Region

Object Ownership: ACLs enabled

Block Public Access: Unchecked (acknowledge warning)

Bucket Versioning: Enabled

Click Create bucket
💡 S3 bucket names are globally unique to avoid conflicts.

### Step 2: Upload Website Content

Open your bucket

Download and unzip these files:
index.html

XYZ - Everyone...love_files.

Go to Objects tab > click Upload

Add index.html and the unzipped folder

Click Upload
HTML (HyperText Markup Language) builds your web pages.

🌐 Step 3: Enable Static Website hosting

Go to the Properties tab of your bucket

Scroll to Static website hosting > click Edit

Enable Static hosting

Hosting type: Host a static website

Index document: index.html

Save changes

Copy the Bucket website endpoint URL

If you see an error, your files are still private. Proceed to the next step.

### Step 4: Make Objects Public

Go to the Objects tab

Select index.html and the image folder files

Click Actions > Make public using ACL

Now reload your website URL — your static site should be live 🎉

Delete Resources
To avoid charges

All S3 objects
The S3 bucket
