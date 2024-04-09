**Mini Project: S3 Static Website Hosting**

**Purpose:**
This mini project guides you through setting up a static website using Amazon S3 static website hosting. You'll create an S3 bucket, upload static website content, configure the bucket for static website hosting, and test the hosted website.

## Overview
This repository includes the files and instructions for hosting "The Coffee Corner" static website using Amazon S3 static website hosting.

### S3 Bucket Details
- Bucket Name: thecoffeecorner
- Website URL: [http://thecoffeecorner.s3-website.eu-west-2.amazonaws.com](http://thecoffeecorner.s3-website.eu-west-2.amazonaws.com)

### Sample Files
You can find the sample files for the website [here](https://github.com/Mayowa2020/the-coffee-corner).

**Objective:**
1. Create an S3 Bucket: Learn to create an S3 bucket in the AWS Management Console.
2. Upload Static Website Content: Upload HTML, CSS, and other static content files to the S3 bucket.
3. Configure S3 for Static Website Hosting: Set up the S3 bucket for static website hosting and configure the index document.
4. Access the Static Website: Verify that the static website is accessible via the provided S3 bucket URL.

## Project Steps
Follow these steps to set up and host "The Coffee Corner" website using Amazon S3 static website hosting:

**Step 1: Create a Bucket**
1. Sign in to the AWS Management Console.
2. Open the Amazon S3 console [here](https://s3.console.aws.amazon.com/s3/home).
3. Click “Create bucket”.
4. Enter Bucket name: thecoffeecorner
5. Choose the Region where you want to create the bucket (geographically close to you for lower latency).
6. Accept the default settings and click “Create”.

**Step 2: Enable Static Website Hosting**
1. After creating the bucket, select it in the S3 console.
2. Choose “Properties.”
3. Under Static website hosting, choose “Edit.”
4. Select “Use this bucket to host a website.”
5. Enable static website hosting by choosing “Enable.”

**Step 3: Configure Index and Error Documents**
1. Enter the Index document file name (usually index.html), which serves as the default page.
2. Optionally, provide a custom Error document file name (e.g., error.html) to handle 404 errors.

**Step 4: Edit Block Public Access Settings**
1. Select the configured static website bucket.
2. Choose “Permissions.”
3. Under Block public access (bucket settings), select “Edit.”
4. Clear “Block all public access” and save changes.

**Step 5: Add a Bucket Policy**
1. Create a bucket policy that makes your bucket content publicly available.
2. For example, you can use the following policy (replace YOUR-BUCKET-NAME with your actual bucket name):
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::thecoffeecorner/*"
       }
     ]
   }
   ```

**Step 6: Test Your Website Endpoint**
1. Once configured, your website endpoint will be in the format: http://thecoffeecorner.s3-website-YOUR-REGION.amazonaws.com.
2. Upload your static website files to the bucket.

**Step 7: Clean Up (Optional)**
- If you no longer need the website, delete the bucket.

**Observations and Insights:**
- Setting up a static website using Amazon S3 is straightforward and requires minimal configuration compared to traditional hosting.
- Hosting from an S3 bucket provides scalability and cost-effectiveness for small to medium-sized websites.
- Ensuring proper permissions and access settings is crucial for making the website publicly accessible while maintaining security.
- Amazon S3 is a reliable solution for hosting static content, making it a popular choice for various web hosting needs.

Feel free to customize the README further based on your project's specific requirements or add more information as needed.

---
