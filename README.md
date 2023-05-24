<img alt="SaaSify logo" align="right" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/66359833-8d0d-4d97-8382-ad5598a5de13>

# Integrating SaaS products with Google Cloud Marketplace
<h1 align="center">Version History</h1>

<table style="width:100%" align="center">
    <tr>
    <th>Version Number</th>
    <th>Date</th>
    <th>Remarks</th>
  </tr
  <tr>
    <td>1.0</td>
    <td>2023-05-23</td>
    <td>GCP Product Setup</td>
  </tr>
</table>

### Contents
- Purpose 
- Prerequisite
- Prerequisite - Service account creation for GCP API access – SaaSify Team
- Product (First Offer) Setup
- Pricing Setup
- Seller Account configuration in SaaSify (SaaSify Team)
- Technical Integration Setup

### Purpose
The document explains the steps to set up a SaaS product in GCP marketplace.

### Prerequisite
Ensure <b>SaaSify tenant</b> is created with <b>GCP</b> as the Provider enabled and <b>Publisher Admin</b> permission is assigned to the Publisher in SaaSify. This can be done with the support of <b>SaaSify Engineering Team</b>.

### Prerequisite - Service account creation for GCP API access – SaaSify Team
A <b>Service Account</b> is required to communicate with GCP Marketplace APIs like <b>Cloud Commerce Partner Procurement API</b> and <b>Service Control API</b> to manage customer purchases, accounts, entitlements, and usage report management.
<p>a. Open the <b>Service Accounts</b> page in the <b> GCP Console</b> (https://console.cloud.google.com/iam-admin/serviceaccounts) under <b>IAM & Admin</b>.</p>
<p>b. Click <b>Create Service Account</b>.</p>
<p>c.	Enter a Service account name (<b>saasify-marketplace-service</b>) and click on <b>Create and Continue.</b></p>
<img alt="Creating a Service Account" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/a4439fd1-0d67-4063-a981-4d1a03811e03>
<p>d. Assign below roles to the Service account and proceed to save the changes:
  <p>• <b>Storage Admin</b> (Cloud storage – Storage admin).</p>
<img alt="Storage Admin" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/bac0bb18-6014-4f0e-a0f8-347ff06c8534>
<br>
 <p>• <b>Service Controller</b> (Service Management - Service Controller).</p>
 <img alt="Service Controller" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/a5cbac2a-9468-4a04-aaa8-377284dfae67>
 <br>
<p>• <b>Editor</b> </p>
 <img alt="Editor" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/f5d474d8-d0fe-463e-965e-d3559f7ef11a>
 <br>
<p>• <b>Pub/Sub Editor</b></p>
<img alt="Pub/Sub Editor" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/feb53efc-2b90-484c-9308-cd34318ed0ec>
<br>
<p>e.	Click on <b>Save</b>. This will create the service account in the below mentioned format -> saasify-marketplace-service@<project domain name>.iam.gserviceaccount.com</p>
<p>f. After creating the <b>Service Account</b> for <b>saasify-(PartnerCompanyName)-public</b> project, click on <b>Manage keys</b> from Actions.</p>
  <img alt="Manage keys" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/1adc4210-ab35-445b-9ed0-c19c5c5701f9>
  <br>
<p>g. Create a <b>Key</b> from the <b>Service Account Console</b> in <b>GCP</b></p>
<img alt="Create a Key" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/ae92d7d8-aa65-4411-aac5-ae05c8c6b187>
<br>
<p>h. Download the <b>JSON</b> key.</p>
<img alt="JSON Key" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/46e6dbe0-0352-448c-8118-12b57ab80abc>
<br>
<p>i.	A key file will be downloaded. Upload this file during the <b>Seller Account</b> creation process in SaaSify as mentioned in the next sections.</p>

### Product (First Offer) Setup
To create a new product/offer in Producer Portal, please follow below GCP documentation:
<p> https://cloud.google.com/marketplace/docs/partners/integrated-saas/set-up-environment </p> 

### Pricing Setup
To setup pricing of a new product/offer in Producer Portal, please follow below GCP documentation:
<p> https://cloud.google.com/marketplace/docs/partners/integrated-saas/select-pricing </p>

### Seller Account configuration in SaaSify (SaaSify Team)
<ol type="a">
  <li>Login to SaaSify (https://app.saasify.ai/) or https://customdomainname.saasify.ai/) for the respective ISV account tenant and create a new seller account for GCP.</li>
  <li>Navigate to Providers > Seller Accounts > click + Seller Accounts.</li>
  <li>Provide the below details in add seller account screen.</li> 
  <img alt="add seller account" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/13fb5f8f-e659-4826-896f-0294c740449d>
  <li>The above step will create a new seller account in SaaSify. In the Seller Accounts list view, click on Edit button.</li>
  <img alt="GCP" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/12ba1e99-3610-44fd-9245-f9b705a39edb>
  <img alt="GCP seller" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/de88b105-52bf-4ec9-94d9-25e11a79a787>
  <br>
  <li>Click on <b>Add Configuration</b></li>
  <li>Select <b>Purchase and Subscription management</b> under the <b>Configuration section</b>.</li>
  <li>Enter <b>Provider Id –</b> This value can be found under Technical Integration of GCP Offer <b>- Partner Procurement API integration</b> as <b>Provider identifier</b>.</li>
  <li>Enter <b>Pub/Sub Topic URL –</b> This value can be found under Technical Integration Section of GCP Offer - <b>Cloud Pub/Sub integration</b> as <b>Pub/Sub topic string</b>.</li>
  <li>Upload Service Account JSON for the service account (<b>saasify-marketplace-service key file)</b> which you have created by clicking on <b>Upload credentials</b>.</li>
  <li>Click on <b>Validate</b> and <b>Save</b>.</li> 
  <li>After saving, now we need to save the following details for use in GCP product definition:</li>
  </ol>
<ul>
  <li>Copy the values for <b>Signup</b> and <b>Login URLs</b> (Required for technical integration update in GCP publisher portal).</li>
  <li>Once the seller account setup is completed, we should be able to see the connection webhook URL is registered/subscribed for the notification under the respective GCP account console pub/sub subscriptions.</li>
  <li>To verify the same, we can follow the steps below.</li>
</ul>
<img alt="Pubsub" src=https://github.com/SaaSifyAdmin/GCP-Productsetup/assets/134104684/97521a2d-04fa-4507-b6d0-c53e8fd78f54>


### Technical Integration Setup
This section defines steps for required technical configuration to integrate SaaSify with Google Cloud Marketplace. 
<ol type="A">
  <li>Navigate to <b>Technical Integration</b> section of the offer in producer-portal.</li> 
  <li>Under <b>Billing Integration</b></li> 
  </ol>
  <ul type="i">
    <li>In the <b>Partner Procurement API Integration</b> section, click <b>Add Service Account</b> and link to the service account <b>saasify-marketplace-service</b> (created in the above section in format saasify-marketplace-service@(project domain name).iam.gserviceaccount.com)</li>
    <li>Project Domain name (Example – Equina-public)</li>
  <li>In the <b>Cloud Pub/Sub Integration</b> section, click <b>Add Service Account</b> and link to the service account <b>saasify-marketplace-service</b> - saasify-marketplace-service@<project domain name>.iam.gserviceaccount.com)</li>
    <li>In the <b>Service control API integration (Only for product with usage fees)</b> section, click </b>Add Service Account</b> and link to the service account <b>saasify-marketplace-service</b> – saasify-marketplace-service@(project domain name).iam.gserviceaccount.com)</li>
  </ul>
    <p>C. Under <b>Frontend Integration</b></p>
<ul type="i">
    <li>Enter the value for Signup URL (above copied from SaaSify Seller Account setup screen)</li> 
    <li>Under Enable SSO login?</li> 
o	Select “No”
  <p>o	Enter the value for Login URL (above copied from Seller Account setup screen)</p> 
</ul>
Once the above steps are performed, you need to perform a test to ensure billing integration is working properly before submitting your product for approval.
<br>
<br>
<p align="center"> © 2023 All rights reserved. SPEKTRA SYSTEMS LLC </p>




