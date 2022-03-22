---
title : "Configure AWS CLI"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

1. Open **Window Command Prompt**, select **`Run as administrator`** mode
2. Type the command **`aws configure`**
3. Enter details from the csv file in [section 2.1.1 Creating access key](../../2-Prerequiste/2.1-useawsmanagementconsole/2.1.1-createaccesskeys/):

     - **AWS Access Key ID**

     - **AWS Secret Access Key**

     - **Default region name**

     - **Default output format:** leave blank

4. Install **Python 2.6** or later.
5. Check python version to confirm successful installation with command **`python --version`**
6. Install Boto3 library with **`pip install boto3`** command