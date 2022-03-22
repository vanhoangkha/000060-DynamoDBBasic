---
title : "Read/Write Capacity Mode"
date :  "`r Sys.Date()`" 
weight : 6 
chapter : false
pre : " <b> 1.6</b> "
---

#### **On-Demand Mode**

- **Amazon DynamoDB on-demand** là một tùy chọn thanh toán linh hoạt có khả năng phục vụ hàng nghìn yêu cầu mỗi giây mà không cần lập kế hoạch dung lượng. **DynamoDB** theo yêu cầu cung cấp giá trả theo yêu cầu cho các yêu cầu đọc và ghi để bạn chỉ trả tiền cho những gì bạn sử dụng.
- Khi bạn chọn chế độ theo yêu cầu, **DynamoDB** ngay lập tức đáp ứng các khối lượng công việc của bạn khi chúng tăng hoặc giảm đến bất kỳ mức lưu lượng truy cập nào đã đạt được trước đó. Nếu mức lưu lượng của khối lượng công việc đạt đến đỉnh mới, DynamoDB sẽ thích ứng nhanh chóng để đáp ứng khối lượng công việc. Các bảng sử dụng chế độ theo yêu cầu cung cấp cùng độ trễ mili giây một chữ số, cam kết thỏa thuận mức dịch vụ (SLA) và bảo mật mà DynamoDB đã cung cấp. Bạn có thể chọn theo yêu cầu cho cả bảng mới và bảng hiện có và bạn có thể tiếp tục sử dụng các **API DynamoDB** hiện có mà không cần thay đổi mã.
- Chế độ theo yêu cầu là một lựa chọn tốt nếu bất kỳ điều nào sau đây là đúng:
  + Bạn tạo bảng mới với khối lượng công việc không xác định.
  + Bạn có lưu lượng ứng dụng không thể đoán trước.
  + Bạn chỉ thích dễ dàng thanh toán cho những gì bạn sử dụng.

#### **Provisioned Mode**
- Nếu bạn chọn chế độ được cấp phép, bạn chỉ định số lần đọc và ghi mỗi giây mà bạn yêu cầu cho ứng dụng của mình. Bạn có thể sử dụng tính năng tự động chia tỷ lệ để tự động điều chỉnh dung lượng được cung cấp của bảng để đáp ứng với những thay đổi về lưu lượng truy cập. Điều này giúp bạn quản lý việc sử dụng DynamoDB của mình để duy trì bằng hoặc thấp hơn tỷ lệ yêu cầu xác định để có được khả năng dự đoán chi phí.
- Chế độ được cung cấp là một tùy chọn tốt nếu bất kỳ điều nào sau đây là đúng:
  + Bạn có lưu lượng ứng dụng có thể dự đoán được.
  + Bạn chạy các ứng dụng có lưu lượng truy cập nhất quán hoặc tăng dần.
  + Bạn có thể dự báo các yêu cầu về năng lực để kiểm soát chi phí.

