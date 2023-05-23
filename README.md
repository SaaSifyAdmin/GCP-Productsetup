# Integrating SaaS products with Google Cloud Marketplace

<h1 align="center">Version History</h1>

|Version Number|Date|Remarks|
| :---: | --- | --- | 
| 1.0 | 2023-05-12 | GCP Product Setup |

### Contents
- Purpose --> 3
- Prerequisite --> 3
- Prerequisite - Service account creation for GCP API access – SaaSify Team -->  3
- Product (First Offer) Setup -->  7
- Pricing Setup -->  7
- Seller Account configuration in SaaSify (SaaSify Team) --> 7
- Technical Integration Setup --> 9

### Purpose
The document explains the steps to set up a SaaS product in GCP marketplace.

### Prerequisite
Ensure SaaSify tenant is created with GCP as the Provider enabled, and Publisher Admin permission is assigned to the Publisher in SaaSify. This can be done with the support of SaaSify Engineering Team.

### Prerequisite - Service account creation for GCP API access – SaaSify Team
A Service Account is required to communicate with GCP Marketplace APIs like Cloud Commerce Partner Procurement API and Service Control API to manage customer purchases, accounts, entitlements, and usage report management.
<p> a.	Open the Service Accounts page in the GCP Console (https://console.cloud.google.com/iam-admin/serviceaccounts) under IAM & Admin.</p>
<p> b. Click Create Service Account.</p>
<p> c.	Enter a service account name (saasify-marketplace-service) and click on Create and Continue</p>
![image](https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/a4439fd1-0d67-4063-a981-4d1a03811e03)
<p> d.Assign below roles to the service account and proceed to save the changes:
![image](https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/bac0bb18-6014-4f0e-a0f8-347ff06c8534)
- Service Controller (Service Management - Service Controller)
![image](https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/a5cbac2a-9468-4a04-aaa8-377284dfae67)
- Editor
![image](https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/f5d474d8-d0fe-463e-965e-d3559f7ef11a)
- Pub/Sub Editor
![image](https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/feb53efc-2b90-484c-9308-cd34318ed0ec)







