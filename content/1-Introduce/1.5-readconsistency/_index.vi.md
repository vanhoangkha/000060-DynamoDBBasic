---
title : "Read Consistency"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 1.5</b> "
---
![Query](/images/1-introduce/1.4-namingrulesanddatatypes/0001-Diagram-Base-Table.png)

#### **Eventually Consistent Reads**
- Khi bạn đọc dữ liệu từ table DynamoDB, phản hồi có thể không phản ánh kết quả của một thao tác ghi đã hoàn thành gần đây.  
- Phản hồi có thể bao gồm một số dữ liệu cũ. 
- Nếu bạn lặp lại yêu cầu đọc của mình sau một thời gian ngắn, phản hồi sẽ trả về dữ liệu mới nhất.
  
![Query](/images/1-introduce/1.5-readconsistency/0001-Diagram-Query.png)

#### **Strongly Consistent Reads**
Khi bạn yêu cầu **Strongly Consistent Reads**, **DynamoDB** trả về phản hồi với dữ liệu cập nhật nhất, phản ánh các cập nhật từ tất cả các hoạt động ghi trước đó đã thành công. Tuy nhiên, tính nhất quán này đi kèm với một số nhược điểm:
- **Strongly Consistent Reads** có thể không khả dụng nếu có sự cố mạng hoặc ngừng hoạt động. Trong trường hợp này, **DynamoDB** có thể trả về **lỗi máy chủ (HTTP 500)**.
- **Strongly Consistent Reads** có thể có độ trễ cao hơn **eventually consistent reads**.
- **Global secondary indexes** không được hỗ trợ **Strongly Consistent Reads**.
- **Strongly Consistent Reads** sử dụng gấp đôi dung lượng thông lượng hơn so với **eventually consistent reads**.
