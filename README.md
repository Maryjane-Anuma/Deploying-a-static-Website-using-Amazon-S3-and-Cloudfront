# Deploying-a-static-Website-using-Amazon-S3-and-Cloudfront
This project demonstrates how I deployed a **personal static website** (resume/portfolio/About Me page) using **Amazon S3** and **CloudFront** under the AWS Free Tier.   The setup allows the website to load faster and more securely via CloudFront’s global CDN.

---

## 🚀 Steps I Took

1. **Created an S3 Bucket**
   - Named my bucket .
   - Disabled “Block all public access”.
   - Enabled **Static Website Hosting** under the “Properties” tab.

    <img width="1908" height="891" alt="cloudfront Distro status" src="https://github.com/user-attachments/assets/6f6c62cd-bfc5-45cf-a1a6-4d619d810422" />

     

2. **Uploaded Website Files**
   - Uploaded `index.html` and `style.css` directly into the bucket.
   - Tested file access using the S3 object URL.

3. **Configured Permissions**
   - Added a **Bucket Policy** to allow public read access:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::my-bucket-name/*"
         }
       ]
     }
     ```
  
     [s3 bucket policy.json](https://github.com/user-attachments/files/22755787/s3.bucket.policy.json)


4. **Enabled Static Website Endpoint**
   - Used the provided endpoint:
     ```
     http://my-bucket-name.s3-website.eu-north-1.amazonaws.com
     ```
     <img width="1908" height="891" alt="Static website hosting" src="https://github.com/user-attachments/assets/8d365b0e-6e2b-4a69-99de-81ea47024304" />


    - Confirmed the website loads successfully over HTTP.

      <img width="1908" height="891" alt="resume deployrd to s3" src="https://github.com/user-attachments/assets/0486a1c8-2f0b-44dd-9a0e-e9973592bd08" />

    

---

## 🧠 What I Learned
- How to use **Amazon S3** as a web host.  
- How to configure **bucket policies** and public permissions securely.  
- Difference between **S3 static hosting** and **EC2 dynamic hosting**.  
- How to structure static websites for cloud deployment.

---

## 💡 Why CloudFront?

CloudFront acts as a Content Delivery Network (CDN) that sits in front of your S3 bucket.

🌍 **Global Speed:** Delivers your site from edge locations closest to visitors.

🔒 **Security:** Supports HTTPS with AWS Certificate Manager (free SSL).

💾 **Caching:** Reduces latency and S3 cost by serving cached content.

📈 **Scalability:** Handles sudden traffic spikes effortlessly.

**Together, S3 + CloudFront make your static website fast, secure, and globally available.**

## 🪄 Tech Stack & Skills
<p align="left"> <img src="https://img.shields.io/badge/AWS%20S3-FF9900?style=for-the-badge&logo=amazons3&logoColor=white"/> <img src="https://img.shields.io/badge/AWS%20CloudFront-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white"/> <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"/> <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white"/> <img src="https://img.shields.io/badge/AWS%20IAM-FF9A00?style=for-the-badge&logo=amazonaws&logoColor=white"/> </p>
