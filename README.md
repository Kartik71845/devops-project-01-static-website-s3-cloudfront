# 🚀 DevOps Project 01 — Deploy Static Website using AWS S3 + CloudFront

![alt text](<Untitled (1).gif>)

This project demonstrates how to host a static website on AWS using **S3 Static Website Hosting** and deliver it globally through **CloudFront CDN**.  
The setup also implements **Block Public Access** on the S3 bucket, allowing CloudFront to access the content securely.

---

## 📌 Architecture Overview

1. **S3 Bucket**
   - Static website hosting enabled
   - Public access fully blocked
   - Bucket policy manually added to allow CloudFront access

2. **CloudFront Distribution**
   - Origin: S3 static website endpoint
   - Default root object: `index.html`
   - HTTP → HTTPS redirection enabled
   - Global CDN caching for faster delivery

3. **Local Setup**
   - Simple `index.html` webpage uploaded to S3
   - Website verified through CloudFront domain

---

## 📁 Folder Structure

project-deploystaticwebsite/
│
├── index.html
├── README.md
└── screenshots/
├── s3-static-hosting.png
├── s3-block-public-access.png
├── bucket-policy.png
├── cloudfront-distribution.png
└── website-working.png


---

## 🛠️ Steps Performed

### **1. Create S3 Bucket**
- Bucket name: `project-deploystaticwebsite`
- Region: (your region)
- Block Public Access: **Enabled**
- Versioning: Optional

### **2. Enable Static Website Hosting**
- Enabled hosting
- Set:
  - Index Document: `index.html`
- Uploaded `index.html` file

### **3. Apply Bucket Policy**
Used the following policy to allow CloudFront to fetch S3 objects:

{
"Version": "2012-10-17",
"Statement": [
{
"Sid": "",
"Effect": "Allow",
"Principal": "",
"Action": "s3:GetObject",
"Resource": "arn:aws:s3:::project-deploystaticwebsite/"
}
]
}


### **4. Create CloudFront Distribution**
- Origin type: **S3 Website Endpoint**
- Viewer protocol: Redirect HTTP → HTTPS
- Default root object: `index.html`
- Disabled access from direct S3 endpoint (website served through CloudFront)

### **5. Test the Deployment**
- Open CloudFront domain URL
- Verified HTML loads correctly
- Screenshots captured

---

## 🌐 Deployed Website (During Execution)

*The CloudFront URL was active during deployment testing.  
The S3 bucket has been removed after project completion to avoid ongoing AWS charges.*

https://d24zzbb1uru3yr.cloudfront.net/


## 🧠 What I Learned
- Hosting static sites on S3
- Difference between **S3 object access** and **S3 website endpoint**
- Configuring CloudFront with S3
- Managing bucket policies with Block Public Access enabled
- Using CloudFront for global caching and HTTPS

---

## 🔗 GitHub Repository Link

https://github.com/Kartik71845/static-website-s3-cloudfront


