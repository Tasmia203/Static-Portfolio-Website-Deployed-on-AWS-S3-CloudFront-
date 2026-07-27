# Cloud-Hosted Portfolio Website Using AWS S3 and CloudFront

## Overview
This project is a static portfolio website hosted entirely on AWS, using **Amazon S3** for storage and **Amazon CloudFront** as a Content Delivery Network (CDN) to serve the site globally with low latency.

**Live site:** https://dz3pqx895ch08.cloudfront.net/

## Architecture

<img width="871" height="718" alt="architecture-diagram" src="https://github.com/user-attachments/assets/4e974a1b-a5fc-42c1-827b-94bc9ad13e5d" />


**How it works:**
1. A user requests the website in their browser.
2. CloudFront checks its cache. If the content isn't cached, it requests it from the S3 bucket.
3. S3 returns the website files to CloudFront.
4. CloudFront delivers the content to the user from the nearest edge location.

## AWS Services Used

### 1. Amazon S3
- Created a bucket named `tasmia-cloud-portfolio` to store the static website file (`index.html`)
- Enabled **Static Website Hosting**
- Attached a bucket policy allowing public `s3:GetObject` access so the site can be served publicly

**Bucket objects:**
<img width="1499" height="746" alt="s3-bucket-objects" src="https://github.com/user-attachments/assets/a6ce61f4-5e66-47a7-9d53-4bbfd1ee0239" />


**Bucket properties:**
<img width="1499" height="696" alt="s3-bucket-properties" src="https://github.com/user-attachments/assets/cbb14bea-5f10-4e0c-926a-60fb8a5d6262" />


**Static website hosting configuration:**
<img width="1504" height="745" alt="s3-static-hosting-config" src="https://github.com/user-attachments/assets/71b9dd9b-9a59-407a-80dd-ebf5e9c15ddc" />


**Bucket policy (public read access, scoped to this bucket only):**
<img width="1501" height="716" alt="bucket-policy" src="https://github.com/user-attachments/assets/dae5f8f2-eb73-4696-be7a-b4de0cd51a7e" />


### 2. Amazon CloudFront
- Created a CloudFront distribution named `tasmia-cloud-portfolio`
- Configured the S3 static website endpoint as the origin
- CloudFront serves the site globally via edge locations for faster load times

<img width="1507" height="692" alt="cloudfront-distribution" src="https://github.com/user-attachments/assets/5d80f842-3202-4d6e-9d6f-11aca7b09c03" />


## Live Website

<img width="1507" height="838" alt="live-site" src="https://github.com/user-attachments/assets/32a7f763-3b56-46c9-90cc-98399d515eb5" />


The site includes:
- Name and title
- About Me section
- Technical skills
- Contact information
- LinkedIn profile link
- Footer noting it's hosted on AWS S3

## Key Takeaways
- Static hosting on S3 is a low-cost, serverless way to host websites without managing infrastructure.
- CloudFront adds caching and global distribution, improving performance and reducing load on the origin.

## Tools Used
- AWS S3 (Static Website Hosting, Bucket Policy)
- AWS CloudFront (CDN)
