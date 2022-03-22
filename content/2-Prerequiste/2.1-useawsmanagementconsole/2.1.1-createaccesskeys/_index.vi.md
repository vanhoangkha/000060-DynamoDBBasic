---
title : "Tạo khóa truy cập"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1.1 </b> "
---

#### **Tạo khóa truy cập cho người dùng IAM**

1. Đăng nhập vào Bảng điều khiển quản lý AWS và mở bảng điều khiển IAM tại [bảng điều khiển IAM](https://console.aws.amazon.com/iam/).

2. Trong thanh điều hướng, chọn **Users**.

![Createaccesskey](/images/2-prerequisite/2.1.1-createaccesskeys/0001-createaccesskey.png) 

3. Chọn tên của người dùng có khóa truy cập bạn muốn tạo, sau đó chọn tab **Security credentials**.

4. Trong phần **Access keys**, chọn **Create access key**.

![Createaccesskey](/images/2-prerequisite/2.1.1-createaccesskeys/0002-createaccesskey.png) 

5. Để xem access key mới, hãy chọn **Show**. Thông tin đăng nhập của bạn sẽ trông giống như sau:
   
```  
Access key ID: AKIAIOSFODNN7EXAMPLE
Secret access key: wJalrXUtnFEMI / K7MDENG / bPxRfiCYEXAMPLEKEY``
```

7. Để tải xuống cặp khóa, hãy chọn  **Download .csv file**. 

![Createaccesskey](/images/2-prerequisite/2.1.1-createaccesskeys/0003-createaccesskey.png) 

8. Sau khi bạn tải xuống tệp  **.csv**, chọn **Close** 