# 🔒🚀 End-to-End AWS S3: Security & Static Web Hosting

## About

I explored Amazon S3 hands-on to learn about secure storage and static website hosting. This project covers:

- **Bucket Restriction Project:** Only the AWS root user can access the bucket.
- **Static Website Hosting Project:** Host a static website on S3, accessible to anyone.

---

## What I Did

- Created and managed S3 buckets
- Enabled versioning and static website hosting
- Wrote custom JSON bucket policies
- Restricted bucket access to the root user
- Hosted a static website for public access
- Used the S3 Standard storage class

---

## Demo Projects

### 1️⃣ Bucket Restriction Project

Restricted an S3 bucket to root user only with this example policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "RootUserOnlyAccess",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:*",
      "Resource": [
        "arn:aws:s3:::your-bucket-name",
        "arn:aws:s3:::your-bucket-name/*"
      ],
      "Condition": {
        "StringNotEquals": {
          "aws:userId": "ROOT-USER-ID-HERE"
        }
      }
    }
  ]
}
```

**Screenshots:**  
<img width="947" height="892" alt="Screenshot 2025-09-29 160353" src="https://github.com/user-attachments/assets/e7587933-2472-4901-8eed-86a09849a85c" />
<img width="1453" height="557" alt="Screenshot 2025-09-29 200727" src="https://github.com/user-attachments/assets/4ca771ec-2e7a-4a60-b74c-49a3c5639784" />
<img width="1697" height="525" alt="Screenshot 2025-10-02 143249" src="https://github.com/user-attachments/assets/c80faacd-37cd-46bc-858b-e87cdd7c23b6" />

---

### 2️⃣ Static Website Hosting Project

Hosted a static website with public read access:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-website-bucket/*"
    }
  ]
}
```

**Screenshots:**  
<img width="1919" height="696" alt="Screenshot 2025-10-02 143453" src="https://github.com/user-attachments/assets/b5bd25cf-39bc-4119-9f70-d8a822843d63" />
<img width="1919" height="773" alt="Screenshot 2025-09-29 185718" src="https://github.com/user-attachments/assets/795caa80-2015-4318-a951-a5306d2e04ed" />
<img width="1915" height="872" alt="Screenshot 2025-09-29 205456" src="https://github.com/user-attachments/assets/9fca8a2b-19fa-4514-b9a9-587429c9fb52" />
<img width="1919" height="836" alt="Screenshot 2025-09-29 205540" src="https://github.com/user-attachments/assets/91618ec7-ad02-4d94-9133-5061ac15f5ae" />
<img width="1919" height="832" alt="Screenshot 2025-09-29 205851" src="https://github.com/user-attachments/assets/43d4d6c1-fc34-4210-bf87-495ce52512d2" />
<img width="1919" height="963" alt="Screenshot 2025-09-29 205903" src="https://github.com/user-attachments/assets/c58a89e0-4e30-476d-b65d-4090ac16a285" />


---

## S3 Storage Classes

Used the **Standard** storage class.  
Other classes include Intelligent-Tiering, Standard-IA, Glacier, etc.
<img width="1280" height="251" alt="image" src="https://github.com/user-attachments/assets/49978354-ac1c-47a2-8dfd-bbf307f2d8d5" />

---

## Summary

This project helped me understand S3 security, bucket policies, and static website hosting in a practical way.

---

**References:**  
- [AWS S3 Docs](https://docs.aws.amazon.com/s3/index.html)  
- [Static Website Hosting](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)  
- [Policy Examples](https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html)  
