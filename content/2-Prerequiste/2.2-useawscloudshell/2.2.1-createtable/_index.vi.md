---
title : "Tạo bảng"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.2.1 </b> "
---


1. Khởi động AWS CloudShell tại [Giao diện CloudShell](https://console.aws.amazon.com/cloudshell/home?region=us-east-1)

2. Gõ lệnh  **`aws configure`**

3. Nhập chi tiết thông tin từ file csv ở phần [2.1.1 Tạo Access key](2.1-useawsmanagenmentconsole/../../../2.1-useawsmanagementconsole/2.1.1-createaccesskeys/):

 - **AWS Access Key ID**
 - **AWS Secret Access Key**
 - **Default region name**
 - **Default output format** 

![Create Table Dashboard!](/images/2-prerequisite/2.2-usecloudshell/2.2.1-createtable/0001-createtable.png "CreateTableDashboard")

4. Để tạo bảng, ta sử dụng lệnh **`create-table`** . Gõ lệnh:
```
aws dynamodb create-table \
    --table-name Music \
    --attribute-definitions \
        AttributeName=Artist,AttributeType=S \
        AttributeName=SongTitle,AttributeType=S \
    --key-schema \
        AttributeName=Artist,KeyType=HASH \
        AttributeName=SongTitle,KeyType=RANGE \
    --provisioned-throughput \
        ReadCapacityUnits=10,WriteCapacityUnits=5 \
    --table-class STANDARD
  ```

5. Kết quả:

- Kết quả trên AWS CloudShell: 

```
{
    "TableDescription": {
        "AttributeDefinitions": [
            {
                "AttributeName": "Artist",
                "AttributeType": "S"
            },
            {
                "AttributeName": "SongTitle",
                "AttributeType": "S"
            }
        ],
        "TableName": "Music",
        "KeySchema": [
            {
                "AttributeName": "Artist",
                "KeyType": "HASH"
            },
            {
                "AttributeName": "SongTitle",
                "KeyType": "RANGE"
            }
        ],
        "TableStatus": "CREATING",
        "CreationDateTime": "2022-02-08T06:15:18.343000+00:00",
        "ProvisionedThroughput": {
            "NumberOfDecreasesToday": 0,
            "ReadCapacityUnits": 10,
            "WriteCapacityUnits": 5
        },
        "TableSizeBytes": 0,
        "ItemCount": 0,
        "TableArn": "arn:aws:dynamodb:us-east-2:089359461550:table/Music",
        "TableId": "4b2a1e9a-c223-4b07-a536-c4b85a67df96",
        "TableClassSummary": {
            "TableClass": "STANDARD"
        }
    }
}
```

- Kết quả trên giao diện:

![Createb Table CloudShell!](/images/2-prerequisite/2.2-usecloudshell/2.2.1-createtable/0002-createtable.png "Createb Table CloudShell")

6. Kiểm tra trạng thái bảng:

- Gõ lệnh: 
```
aws dynamodb describe-table --table-name Music | grep TableStatus
```

- Khi DynamoDB hoàn thành việc tạo bảng, giá trị của **TableStatus** là **ACTIVE**: `"TableStatus": "ACTIVE",`