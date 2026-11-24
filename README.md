# Risk-assessment
# ASSET-ORIENTED RISK ASSESSMENT OF STORAGE ASSETS IN AWS AND AZURE

## OBJECTIVE

To identify storage assets in AWS S3 and Microsoft Azure Blob Storage, identify possible vulnerabilities and threats, assess their likelihood and impact, calculate risk levels, and recommend suitable security measures.

## REQUIREMENTS

- AWS Account
- Microsoft Azure Account
- Web Browser
- Internet Connection

## CLOUD SERVICES USED

- AWS – Amazon S3
- Microsoft Azure – Azure Blob Storage

## PART A – AWS S3 STORAGE ASSESSMENT

### Step 1: Access Amazon S3

1. Log in to the AWS Management Console.
2. Search for **S3** in the search bar.
3. Select **Amazon S3**.

### Step 2: Examine S3 Bucket Details

1. Open the **Buckets** section.
2. Select the bucket created in the previous experiment.
3. Examine the bucket overview.
4. Record the bucket name, AWS region, and number of objects.

**Observed Details:**

- Bucket Name: `cloudtrail-audit-test-2026-kv`
- AWS Region: `us-east-1`
- Number of Objects: `0`

<img width="1600" height="812" alt="image" src="https://github.com/user-attachments/assets/e1510021-4215-4473-a3ce-a3bce05d0fb0" />


### Step 3: Check Block Public Access

1. Open the selected S3 bucket.
2. Go to the **Permissions** tab.
3. Find the **Block public access** section.
4. Check whether all public access is blocked.

**Observed Configuration:**

- Block All Public Access: **ON**

<img width="1600" height="807" alt="image" src="https://github.com/user-attachments/assets/80ecd31f-3dd0-4456-ae87-39f06a02902a" />


### Step 4: Check Bucket Versioning

1. Open the **Properties** tab.
2. Find the **Bucket Versioning** section.
3. Check whether versioning is enabled or disabled.

**Observed Configuration:**

- Bucket Versioning: **Disabled**

<img width="1600" height="815" alt="image" src="https://github.com/user-attachments/assets/abf421b6-c6da-4928-b929-904bf5fb5550" />


### Step 5: Check Default Encryption

1. Open the **Properties** tab.
2. Find the **Default encryption** section.
3. Check the encryption method used by the bucket.

**Observed Configuration:**

- Encryption Type: **SSE-S3**
- Encryption Status: **Enabled**
- Key Management: **Amazon S3 managed keys**

<img width="1600" height="814" alt="image" src="https://github.com/user-attachments/assets/c3f4e00d-3545-40c0-8bee-155b8ea95a20" />


### Step 6: Check Bucket Policy

1. Open the **Permissions** tab.
2. Find the **Bucket policy** section.
3. Check whether a bucket policy is configured.

**Observed Configuration:**

- Bucket Policy: **No policy configured**

<img width="1600" height="823" alt="image" src="https://github.com/user-attachments/assets/6d9f5fc9-0a4d-44a1-8218-584cd0dfb876" />


### Step 7: Check Object Ownership and ACL

1. Open the **Permissions** tab.
2. Find the **Object Ownership** section.
3. Check the ownership setting and ACL status.

**Observed Configuration:**

- Object Ownership: **Bucket owner enforced**
- ACLs: **Disabled**

<img width="1600" height="819" alt="image" src="https://github.com/user-attachments/assets/be0914c9-2d31-406c-8275-a2ee11db3eb8" />


### Step 8: Check Server Access Logging

1. Open the **Properties** tab.
2. Find the **Server access logging** section.
3. Check whether logging is enabled or disabled.

**Observed Configuration:**

- Server Access Logging: **Disabled**

<img width="1600" height="817" alt="image" src="https://github.com/user-attachments/assets/b9ec905b-a985-4b42-9244-82ffd2e6a757" />


---

## PART B – AWS S3 RISK ASSESSMENT

Risk assessment is performed by identifying possible threats and calculating their risk scores.

### Risk Score Formula

**Risk Score = Likelihood × Impact**

### Likelihood Scale

| Score | Likelihood |
|---|---|
| 1 | Very Low |
| 2 | Low |
| 3 | Medium |
| 4 | High |
| 5 | Very High |

### AWS S3 Risk Assessment Table

| Storage Asset | Identified Risk | Possible Threat | Likelihood | Impact | Risk Score | Risk Level | Recommended Mitigation |
|---|---|---|---:|---:|---:|---|---|
| S3 Bucket | Versioning disabled | Accidental or malicious data deletion | 3 | 4 | 12 | High | Enable versioning |
| S3 Bucket | Access logging disabled | Difficult investigation of unauthorized activity | 3 | 3 | 9 | Medium | Enable appropriate logging |

### Risk Observation

1. Versioning is disabled, which may make data recovery difficult after accidental deletion or modification.
2. Server access logging is disabled, which may make it difficult to investigate suspicious activities.
3. Block Public Access is enabled, helping prevent unintended public access.
4. Default encryption using SSE-S3 is enabled.
5. Bucket owner enforced is enabled and ACLs are disabled.
6. No bucket policy is configured. This is not considered a vulnerability by itself.

---

## PART C – SECURITY RECOMMENDATIONS

1. Enable Block Public Access to prevent unintended public exposure.
2. Enable S3 Versioning to recover accidentally deleted or modified objects.
3. Enable appropriate logging to monitor bucket activity.
4. Apply least-privilege IAM permissions.
5. Use server-side encryption to protect stored data.
6. Regularly review bucket policies and access permissions.
7. Disable ACLs and use policy-based access control where appropriate.

---

## PART D – AZURE RISK ASSESSMENT

Prepare the following table using the **actual configuration observed**.

| Asset | Vulnerability | Threat | Likelihood | Impact | Risk Score | Risk Level | Recommended Mitigation |
|---|---|---|---:|---:|---:|---|---|
| Azure Blob Storage | Anonymous access enabled* | Unauthorized data access | 4 | 5 | 20 | Critical | Disable anonymous access |
| Azure Storage | Data protection disabled* | Permanent data loss | 3 | 4 | 12 | High | Enable appropriate protection |
| Azure Storage | Excessive permissions* | Unauthorized modification | 3 | 4 | 12 | High | Apply least privilege |
| Azure Storage | Unrestricted network access* | External attack/access | 3 | 4 | 12 | High | Restrict network access |

**Note:** The asterisk (*) indicates a possible vulnerability. Confirm the actual Azure configuration before including it as an observed risk.

## PART E – AZURE BLOB STORAGE RISK ASSESSMENT

The Azure storage configuration is assessed by identifying possible risks, their likelihood, and their impact.

### Risk Score Formula

**Risk Score = Likelihood × Impact**

### Azure Risk Assessment Table

| Storage Asset | Identified Risk | Possible Threat | Likelihood | Impact | Risk Score | Risk Level | Recommended Mitigation |
|---|---|---|---:|---:|---:|---|---|
| Azure Blob Storage | Anonymous access enabled* | Unauthorized data access | 4 | 5 | 20 | Critical | Disable anonymous access |
| Azure Storage | Data protection disabled* | Permanent data loss | 3 | 4 | 12 | High | Enable appropriate protection |
| Azure Storage | Excessive permissions* | Unauthorized modification | 3 | 4 | 12 | High | Apply least privilege |
| Azure Storage | Unrestricted network access* | External attack or access | 3 | 4 | 12 | High | Restrict network access |

**Note:** The asterisk (*) indicates a possible risk scenario, not a verified finding. Confirm the actual Azure settings before marking any risk as observed.

---

## PART F – AWS AND AZURE SECURITY COMPARISON

| Security Feature | AWS S3 | Azure Blob Storage |
|---|---|---|
| Public Access Control | Block Public Access | Anonymous Access Control |
| Encryption | SSE-S3 / SSE-KMS | Azure Storage Encryption |
| Versioning | S3 Versioning | Blob Versioning |
| Data Recovery | Versioning and other recovery controls | Soft Delete and Versioning |
| Access Control | IAM and Bucket Policies | RBAC and Access Policies |
| Logging and Monitoring | S3 Logging and Cloud Monitoring | Azure Monitoring and Logging |
| Network Security | Bucket and network controls | Storage Networking and Private Endpoints |

---
## RESULT

The storage assets in AWS S3 and Microsoft Azure Blob Storage were studied for their security configurations and possible vulnerabilities. Risks were identified based on their likelihood and impact, and risk scores were calculated using the formula **Risk Score = Likelihood × Impact**. Suitable security recommendations were provided to improve cloud storage security and protect stored data.
