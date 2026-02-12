# aws-s3-cloudfront-static-website
Private S3 bucket secured with CloudFront using Origin Access Control (OAC) via CloudFormation
# 🚀 Private S3 + CloudFront using Origin Access Control (OAC)

This project demonstrates a **secure static website architecture** using AWS CloudFormation.

The S3 bucket is **completely private** and accessible **only through CloudFront** using **Origin Access Control (OAC)**.

---

## 🏗️ Architecture Overview

User → CloudFront (HTTPS) → OAC → Private S3 Bucket  

Direct public access to S3 is fully blocked.

### Architecture Diagram
![Architecture Diagram](docs/architecture-diagram.png)

---

## 🧱 AWS Resources Created

### ✅ S3 Bucket (Private)
- Bucket Versioning enabled
- Server-side encryption (AES256)
- Block all public access enabled

### ✅ CloudFront Origin Access Control (OAC)
- Signing Protocol: SigV4
- Signing Behavior: Always
- Secure access to private S3 bucket

### ✅ CloudFront Distribution
- HTTPS enabled
- Default root object: `index.html`
- Viewer protocol: Redirect HTTP → HTTPS

### ✅ S3 Bucket Policy
- Allows access **only from CloudFront**
- Uses `AWS:SourceArn` condition
- Prevents direct S3 object access

---

## 🔐 Security Best Practices Applied

- S3 Public Access Block: Enabled
- Bucket Encryption: Enabled
- CloudFront HTTPS: Enabled
- Direct S3 access: Blocked
- OAC Authentication: Enabled

---

## 📤 CloudFormation Stack Output

- **Bucket Name**: Private S3 bucket
- **CloudFront URL**: Secure HTTPS endpoint

---

## 📸 Screenshots

### CloudFormation Template
![CloudFormation Template](cloudfront-s3-oac.yaml.png)

### CloudFormation Outputs
![Stack Outputs](stack-output.png)

### Private S3 Bucket Settings
![Private S3 Bucket](Privtae-S3-Bucket.png)

---

## 🚀 Deployment Steps

1. Open AWS CloudFormation Console
2. Create Stack → Upload CloudFormation template
3. Wait for `CREATE_COMPLETE`
4. Open CloudFront URL from Outputs

---

## 🎯 What I Learned

- Secure static hosting using CloudFront OAC
- Writing secure S3 bucket policies
- Using Infrastructure as Code (CloudFormation)
- Implementing AWS security best practices

---

## 🛠️ Technologies Used

- AWS S3
- AWS CloudFront
- Origin Access Control (OAC)
- AWS CloudFormation
- IAM Policies
