# Serverless Feedback Logger using AWS (S3, Lambda & CloudWatch)

## 📌 Project Overview

Many applications require user feedback to improve services. Traditional feedback collection systems require servers and manual monitoring. This project demonstrates a **serverless feedback collection system using AWS** that automatically processes feedback files uploaded by users.

The system uses **Amazon S3, AWS Lambda, and Amazon CloudWatch** to build a scalable and cost-efficient feedback processing pipeline.

---

# 🏗 Architecture

The system follows a simple event-driven architecture:

1. Users upload feedback files (.txt or .json) to an **Amazon S3 bucket**
2. S3 triggers an **AWS Lambda function**
3. Lambda reads and processes the feedback file
4. The feedback content is logged into **Amazon CloudWatch**

---

# ☁ AWS Services Used

| Service           | Purpose                                   |
| ----------------- | ----------------------------------------- |
| Amazon S3         | Stores feedback files uploaded by users   |
| AWS Lambda        | Processes feedback automatically          |
| Amazon CloudWatch | Stores logs and monitors Lambda execution |
| AWS IAM           | Manages permissions between services      |

---

# 🔄 Workflow

1️⃣ User uploads feedback file to S3 bucket
2️⃣ S3 event triggers Lambda function
3️⃣ Lambda reads the uploaded file
4️⃣ Feedback content is logged in CloudWatch

---

# 📂 Project Structure

```
serverless-feedback-logger-aws
│
├── lambda
│   └── lambda_function.py
│
├── sample-feedback
│   ├── feedback1.json
│   └── feedback2.txt
│
├── screenshots
│
└── README.md
```

---

# ⚙ Implementation Steps

## Step 1: Create S3 Bucket

* Navigate to AWS Console → S3
* Create bucket (example: `feedback-collection-system`)
* Optionally create folder `uploads/`

📷 Screenshot:

![S3 Bucket](<img width="1004" height="507" alt="image" src="https://github.com/user-attachments/assets/042e2b5d-bfda-4238-a0aa-cb4e55044a15" />
)

---

## Step 2: Create Lambda Function

* Go to AWS Console → Lambda
* Runtime: **Python 3.12**
* Name: `feedbackserviceL`

Add S3 trigger:

* Event type: **Object Created**
* Prefix: `uploads/`
* Suffix: `.json` or `.txt`

📷 Screenshot:

![Lambda](<img width="1004" height="506" alt="image" src="https://github.com/user-attachments/assets/07590009-8ccd-44c3-9e5d-a59c56e28bc8" />
)

---

## Step 3: Configure IAM Permissions

Attach policies to Lambda role:

* `AmazonS3ReadOnlyAccess`
* `CloudWatchLogsFullAccess`

📷 Screenshot:

![IAM](<img width="1004" height="505" alt="image" src="https://github.com/user-attachments/assets/c7160db5-2489-47f6-88c9-bf36c2ffde10" />
)

---

## Step 4: View Logs in CloudWatch

Navigate to:

CloudWatch → Log Groups → `/aws/lambda/feedbackserviceL`

📷 Screenshot:

![CloudWatch](<img width="1004" height="498" alt="image" src="https://github.com/user-attachments/assets/86dadfdb-ddb3-4ce6-b6cd-f531f47b76ab" />
)

---

# 📊 Expected Outcome

* Feedback files uploaded to S3 are automatically processed
* Lambda reads and logs the feedback
* CloudWatch stores logs for monitoring and debugging
* Fully automated serverless workflow

---

# 🚀 Benefits

✔ Serverless architecture
✔ Scalable and event-driven
✔ Low operational cost
✔ No infrastructure management

---

# 📌 Future Improvements

* Store feedback in **DynamoDB**
* Create **API Gateway for real-time submission**
* Build a **dashboard using AWS QuickSight**

---

# 👨‍💻 Author

B Poorvi Shasta
Cloud Computing Project
