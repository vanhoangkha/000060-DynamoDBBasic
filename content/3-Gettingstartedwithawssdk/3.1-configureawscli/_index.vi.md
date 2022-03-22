---
title : "Cấu hình AWS CLI"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

1. Mở **Window Command Prompt**, chọn chế độ **`Run as administrator`**
2. Gõ lệnh **`aws configure`**
3. Nhập chi tiết thông tin từ file csv ở [phần 2.1.1 Tạo access key](../../2-Prerequiste/2.1-useawsmanagementconsole/2.1.1-createaccesskeys/):

    - **AWS Access Key ID**

    - **AWS Secret Access Key**

    - **Default region name**

    - **Default output format:** bỏ trống

4. Cài đặt **Python 2.6** trở lên.
5. Kiểm tra version python để xác định đã cài đặt thành công bằng lệnh **`python --version`**
6. Cài đặt thư viện Boto3 bằng lệnh **`pip install boto3`**
