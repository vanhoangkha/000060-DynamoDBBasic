---
title : "Bắt đầu với AWS SDK"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

{{% notice info %}}
Để thực hiện bước này, bạn cần tạo Access key được sử dụng để định cấu hình AWS CLI và cài đặt Python và Boto3.
{{% /notice %}}

SDK bao gồm hai gói Python chính: Botocore (thư viện cung cấp chức năng cấp thấp được chia sẻ giữa Python SDK và AWS CLI) và Boto3 (gói triển khai Python SDK chính).

Trong bài lab này, chúng ta sử dụng Boto3

**Clients** cung cấp giao diện cấp thấp cho dịch vụ AWS. Định nghĩa của chúng được tạo bởi mô tả dịch vụ JSON có trong thư viện botocore. Gói botocore được chia sẻ giữa boto3 cũng như AWS CLI.

Định nghĩa dịch vụ cho AWS S3 được lưu trữ dưới dạng JSON trong gói botocore.

Các lợi ích chính của việc sử dụng ứng dụng Boto3 Client là:

- Nó ánh xạ 1: 1 với API dịch vụ AWS thực tế.
- Tất cả các hoạt động dịch vụ AWS đều được hỗ trợ bởi Clients.

Ví dụ: nếu bạn muốn liệt kê tất cả các S3 buckets trong tài khoản AWS của mình, bạn có thể sử dụng Ứng dụng Clients S3 như sau:

```
import boto3

# Retrieve the list of existing buckets

s3 = boto3.client("s3")
response = s3.list_buckets()

# Output the bucket names

print("Existing buckets:")
for bucket in response['Buckets']:
    print(f'{bucket["Name"]}')

```

** Resource ** là một mức trừu tượng cao hơn các máy khách. Chúng được tạo từ mô tả Resource JSON có trong chính thư viện boto.

Resource cung cấp giao diện hướng đối tượng để tương tác với các dịch vụ AWS khác nhau. Resource có thể được khởi tạo như sau:

{{% notice tip%}}
 Ví dụ dưới đây là định nghĩa Resource cho S3.
{{% /notice %}}

```
import boto3

s3 = boto3.resource("s3")

```

### Nội dung
  - [Cấu hình AWS CLI](3.1-configureawscli/)
  - [Python và DynamoDB](3.2-pythonandynamodb/)