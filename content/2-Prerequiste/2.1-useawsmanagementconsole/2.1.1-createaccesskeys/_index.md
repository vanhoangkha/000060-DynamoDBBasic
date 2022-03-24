---
title : "Create access key"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1.1 </b> "
---

#### **Generate access keys for IAM users**

1. Sign in to the AWS Management Console and open the IAM console at [IAM console](https://console.aws.amazon.com/iam/).

2. In the navigation bar, select **Users**.

![Createaccesskey](/images/2-prerequisite/2.1.1-createaccesskeys/0001-createaccesskey.png)

3. Select the name of the user whose access key you want to create, and then select the **Security credentials** tab.

4. In the **Access keys** section, select **Create access key**.

![Createaccesskey](/images/2-prerequisite/2.1.1-createaccesskeys/0002-createaccesskey.png)

5. To view the new access key, select **Show**. Your login information should look like this:
   
```
Access key ID: AKIAIOSFODNN7EXAMPLE
Secret access key: wJalrXUtnFEMI / K7MDENG / bPxRfiCYEXAMPLEKEY``
```

6. To download the key pair, select **Download .csv file**.

![Createaccesskey](/images/2-prerequisite/2.1.1-createaccesskeys/0003-createaccesskey.png)

7. After you download the **.csv** file, select **Close**
