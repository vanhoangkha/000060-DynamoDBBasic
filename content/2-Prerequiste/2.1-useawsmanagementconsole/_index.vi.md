---
title : "Sử dụng AWS Management Console"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---
Bạn có thể truy cập table điều khiển quản lý AWS cho Amazon DynamoDB tại [table điều khiển quản lý AWS cho Amazon DynamoDB](https://console.aws.amazon.com/dynamodb/home).

Bạn có thể sử dụng table điều khiển để thực hiện những việc sau trong DynamoDB:

- Theo dõi các cảnh báo gần đây, tổng dung lượng, tình trạng dịch vụ và tin tức DynamoDB mới nhất trên bảng điều khiển DynamoDB.

- Tạo, cập nhật và xóa table. Máy tính công suất cung cấp ước tính về số lượng đơn vị dung lượng cần yêu cầu dựa trên thông tin sử dụng bạn cung cấp.

- Quản lý luồng.

- Xem, thêm, cập nhật và xóa các mục được lưu trữ trong table. **Quản lý thời gian tồn tại (TTL)** để xác định thời điểm các mục trong table hết hạn để chúng có thể tự động bị xóa khỏi cơ sở dữ liệu.

- Truy vấn và quét table.

- Thiết lập và xem cảnh báo để giám sát việc sử dụng công suất của table. Xem các chỉ số giám sát hàng đầu của table của bạn trên biểu đồ thời gian thực từ **CloudWatch**.

- Sửa đổi dung lượng được cung cấp của table.

- Sửa đổi lớp table của table.

- Tạo và xóa các Secondary Index toàn cầu.

- Tạo trình kích hoạt để kết nối các luồng DynamoDB với các chức năng AWS Lambda.

- Áp dụng các tag cho tài nguyên của bạn để giúp tổ chức và xác định chúng.

- Mua dung lượng dự trữ ( reversed capacity).

{{% notice info %}}
Nếu bạn có thể dự đoán nhu cầu của mình đối với thông lượng đọc và ghi của Amazon DynamoDB, thì dung lượng dự trữ sẽ tiết kiệm đáng kể so với mức giá bình thường của dung lượng thông lượng được DynamoDB cung cấp. Bạn trả phí trả trước một lần và cam kết thanh toán cho mức sử dụng tối thiểu với mức giá cụ thể theo giờ trong suốt thời hạn dung lượng đã bảo lưu.
{{% /notice %}}

![DYNAMODB AWS](/images/2-prerequisite/2.1-useawsconsole/0001-dynamodbhome.png)

Management console hiển thị màn hình giới thiệu nhắc bạn tạo table đầu tiên của mình. Để xem các table của bạn, trong thanh điều hướng ở phía bên trái của table điều khiển, hãy chọn **Tables** .

Dưới đây là tổng quan cấp cao về các tác vụ có sẵn trên mỗi table trong mỗi tab điều hướng:

- **Tổng quan** - Xem chi tiết table, bao gồm số lượng mục và số liệu.

- **index** - Quản lý các index thứ cấp toàn cầu và cục bộ.

- **Monitoring** - Xem báo thức, Thông tin chi tiết về cộng tác viên CloudWatch và các chỉ số Cloudwatch.

- **Global table** - Quản lý bản sao table.

- **Backup** - Quản lý khôi phục tại thời điểm và sao lưu theo yêu cầu.

- **Export & Stream** - Xuất table của bạn sang Amazon S3 và quản lý Luồng DynamoDB và Luồng dữ liệu Kinesis.

- **Cài đặt bổ sung** - Quản lý dung lượng đọc / ghi, cài đặt Thời gian tồn tại, mã hóa và tag.